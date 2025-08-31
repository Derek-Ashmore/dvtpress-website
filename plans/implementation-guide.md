# Implementation Guide for Adding New Books

## Quick Start

1. **Prepare your book data** using one of the provided formats (JSON recommended)
2. **Prepare your images** (cover image and optional author photo)
3. **Submit the data** in your preferred format
4. The book will be added to the website following the existing structure

## Step-by-Step Process

### Step 1: Gather Book Information
Collect all required information:
- Book title and author name
- Book cover image (high quality)
- Description (2-3 paragraphs)
- Publication status
- Purchase links (Amazon, B&N, etc.)

### Step 2: Prepare Images
- Save cover image as: `book-title-cover.jpg`
- Recommended dimensions: 300x450px minimum
- Optimize for web (compress if needed)
- Place in the `images/` folder

### Step 3: Format Your Data
Use one of these templates:
- `book-data-template.json` - Blank template
- `example-book-entry.json` - Filled example
- Or use the Markdown/YAML formats from the requirements doc

### Step 4: Create HTML Page
The HTML page will be generated with:
- Consistent header and navigation
- Book information display
- Purchase links section
- Optional tabbed interface for detailed books
- Responsive design matching existing site

### Step 5: Update Navigation
The new book will be added to the navigation menu in all pages:
```html
<nav>
  <ul>
    <li><a href="/">Home</a></li>
    <li><a href="java-ee-architects-handbook-second-edition.html">Java EE Handbook</a></li>
    <li><a href="microservices-for-java-architects.html">Microservices for Architects</a></li>
    <li><a href="your-new-book.html">Your New Book</a></li> <!-- Added -->
    <li><a href="news.html">News</a></li>
    <li><a href="book-seller.html">Book Sellers</a></li>
  </ul>
</nav>
```

### Step 6: Test and Verify
- Check all links work correctly
- Verify images display properly
- Test navigation from all pages
- Ensure responsive design works on mobile

## HTML Structure for Different Book Types

### Simple Book Page (like Microservices book)
```html
<article>
  <h1>Book Title</h1>
  <h2>by Author Name</h2>
  <div class="photo">
    <img src="images/book-cover.jpg" align="right" />
  </div>
  <p>Description paragraph 1...</p>
  <p>Description paragraph 2...</p>
  <p>Publication status</p>
</article>
```

### Detailed Book Page with Tabs (like Java EE Handbook)
Uses jQuery UI tabs for organizing:
- Buy tab (purchase links)
- Details tab (extended description)
- Table of Contents tab
- Resources and Errata tab
- Author tab
- Reviews tab

## File Organization

```
dvtpress-website/
├── site/
│   ├── images/
│   │   ├── book-covers/        # Book cover images
│   │   └── author-photos/      # Author photos
│   ├── docs/                   # Downloadable resources
│   ├── style.css              # Site styling
│   ├── index.html             # Home page
│   ├── [book-name].html       # Individual book pages
│   └── book-seller.html       # Retailers page
└── plans/
    ├── new-book-data-requirements.md    # This documentation
    ├── book-data-template.json         # Blank template
    ├── example-book-entry.json         # Example with data
    └── implementation-guide.md          # This guide
```

## Data Validation Checklist

Before submitting book data, ensure:
- [ ] Title is complete and accurate
- [ ] Author name(s) spelled correctly
- [ ] Cover image is high quality
- [ ] Description is compelling and error-free
- [ ] All purchase links are valid
- [ ] ISBN is correct (if provided)
- [ ] Table of contents is complete (if provided)
- [ ] Reviews have proper attribution (if provided)
- [ ] Download links work (if provided)

## Common Issues and Solutions

### Issue: Book appears in wrong order in navigation
**Solution:** Specify the desired position in the navigation order

### Issue: Cover image appears too large/small
**Solution:** Ensure image is properly sized (300x450px recommended)

### Issue: Tabs not working on detailed book page
**Solution:** Verify jQuery UI scripts are properly loaded

### Issue: Purchase links not working
**Solution:** Test all URLs before submission

## Support

For questions about adding new books to the site:
1. Review the requirements document
2. Check the example JSON file
3. Follow this implementation guide

The system is designed to make adding new books straightforward while maintaining consistency with the existing site design.