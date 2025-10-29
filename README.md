# Click Actions Template

This document describes the click actions for all interactive elements in the PanKbase Data Library mockup.
## Note: The header and footer remains in sync with the PKB main site i.e. pankbase.org
## Implementation Approach

Each interactive element uses HTML5 data attributes to define its behavior:
- `data-action`: Type of action (download, navigate, browse)
- `data-resource` or `data-page` or `data-category`: Identifier for the action
- `data-url`: Target URL for the action

## Carousel Items - Data Downloads

All carousel items have `data-action="download"` and trigger download functionality.

| Item | Data Resource | Data URL | Action |
|------|--------------|----------|--------|
| **PanKbase scRNA UMAP** | `pankbase-scrna-umap` | `/download/pankbase-scrna-umap` | Downloads zip file of single-cell RNA sequencing UMAP object, cell by gene matrix, metadata and UMAP coordinates |
| **DEG Analysis** | `deg-analysis` | `/download/deg-analysis` | Downloads differential gene expression analysis results for all cell tyes + accompying metadata as zip file |
| **snATAC Marker Peaks** | `snatac-marker-peaks` | `/download/snatac-marker-peaks` | Downloads marker peaks data for each cell types + metadata as zip file |
| **snATAC UMAP** | `snatac-umap` | `/download/snatac-umap` | Downloads snATAC UMAP visualization (91K nuclei) cell by peak matrix, metadata and UMAP coordinate|
| **PanKbase Donors** | `pankbase-donors` | `/download/pankbase-donors` | Downloads donor metadata (3.7K donors) in tsv format |
| **PanKbase Biosamples** | `pankbase-biosamples` | `/download/pankbase-biosamples` | Downloads biosample data (3.6K samples) in tsv format|

**Handler Function**: `handleDownload(resource, url, title)`

**Current Implementation**: Shows alert with download information

**Future Implementation**:
```javascript
function handleDownload(resource, url, title) {
    // Option 1: Direct download link
    window.location.href = url;
    
    // Option 2: API call with download
    fetch(url, { method: 'GET' })
        .then(response => response.blob())
        .then(blob => {
            const downloadUrl = window.URL.createObjectURL(blob);
            const a = document.createElement('a');
            a.href = downloadUrl;
            a.download = `${resource}.zip`;
            document.body.appendChild(a);
            a.click();
            document.body.removeChild(a);
        });
}
```

---

## Tools & Resources Section - Navigation

All cards in the Tools & Resources section have `data-action="navigate"` and navigate to specific pages.

| Card | Data Page | Data URL | Action |
|------|-----------|----------|--------|
| **API Access** 🔌 | `api` | `/api` | Navigates to API documentation and access page |
| **Scripts** {'</>'} | `scripts` | `/scripts` | Navigates to data exploration scripts github |
| **Data Standards** 📋 | `data-standards` | `/data-standards` | Navigates to schema and metadata standards page |
| **User Guide** 📖 | `user-guide` | `/user-guide` | Navigates to comprehensive user guide |
| **Data Library News** 📰 | `news` | `/news` | Navigates to news and announcements page |

**Handler Function**: `handleNavigate(page, url, title)`

**Current Implementation**: Shows alert with navigation information


---

## Data Access Section - Browse

All cards in the Data Access section have `data-action="browse"` and filter/browse specific categories.

| Card | Data Category | Data URL | Action |
|------|---------------|----------|--------|
| **Donors** 👥 (3.7K) | `donors` | `/browse/donors` | Browses human donor data (3.7K records) on DL |
| **Biosamples** 🧪 (3.6K) | `biosamples` | `/browse/biosamples` | Browses pancreatic biosample collection (3.6K records) on DL |
| **Assays** 🔬 (627) | `assays` | `/browse/assays` | Browses experimental assays (627 records) on DL|
| **Intermediate Analysis Results** 📊 (378) | `intermediate-results` | `/browse/intermediate-results` | Browses processed results (378 records) on DL|
| **Resource Analysis** 📦 (3) | `resource-analysis` | `/browse/resource-analysis` | Browses analysis resources (3 records) on DL|
| **Principal Analysis Results** 📈 (47) | `principal-results` | `/browse/principal-results` | Browses final analysis results (47 records) on Dl|
| **Workflows** ⚙️ (5) | `workflows` | `/browse/workflows` | Browses analysis workflows (5 records) on DL|

**Handler Function**: `handleBrowse(category, url, title)`

**Current Implementation**: Shows alert with browse information

**Future Implementation**:
```javascript
function handleBrowse(category, url, title) {
    // Navigation with category filter
    window.location.href = url;
    
    // Or with query parameters
    // window.location.href = `/browse?category=${category}`;
    
    // Or dynamic content loading
    // loadBrowseView(category);
    
    // Or set filter state
    // setFilter({ category: category });
}
```

---

## Search Bar Actions

**Location**: Search section at the top of the page

**Elements**:
- Search input field
- Search button

**Current Implementation**: fuzzy search

---

## Action Flow Summary

```
User Click Event
    ↓
Check data-action attribute
    ↓
    ├─→ "download" → handleDownload(resource, url, title)
    │                    ↓
    │                   Implement: Download file/resource
    │
    ├─→ "navigate" → handleNavigate(page, url, title)
    │                    ↓
    │                   Implement: Navigate to page/route
    │
    └─→ "browse" → handleBrowse(category, url, title)
                       ↓
                      Implement: Filter/browse category on DL
```

---

## TODO for Full Implementation

### 1. Download Functionality
- [ ] Implement file download for carousel items
- [ ] Add download progress indicator
- [ ] Handle large file downloads
- [ ] Add authentication if required
- [ ] Implement download tracking

### 2. Navigation
- [ ] Add News Section
- [ ] Improve API documentation

### 3. Browse Functionality
- [ ] Revisit filters and Summary


### 6. Additional Enhancements
- [ ] Add loading states
- [ ] Implement error handling
- [ ] Add analytics tracking
- [ ] Implement user preferences (theme, etc.)
- [ ] Add keyboard shortcuts

---

## Testing Checklist

- [ ] All carousel items trigger download
- [ ] All Tools & Resources cards navigate correctly
- [ ] All Data Access cards browse correctly
- [ ] Search functionality works
- [ ] Navigation menu works
- [ ] Active states update correctly
- [ ] Mobile responsive behavior
- [ ] Keyboard navigation support
- [ ] Browser back/forward buttons work
- [ ] All URLs are accessible

---

## Notes

- All action handlers are currently placeholder implementations showing alerts
- Data attributes provide a clean separation between HTML structure and JavaScript behavior
- The template approach makes it easy to wire up actual functionality later
- Console logs are included for debugging during development
- All handler functions follow a consistent pattern for easy maintenance

