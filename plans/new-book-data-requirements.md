# New Book Data Requirements for DVT Press Website

## Overview
This document outlines the data requirements and preferred format for adding new books to the DVT Press static website.

## Required Book Information

### Core Fields (Required)
1. **Book Title** - The full title of the book
2. **Author Name(s)** - Primary author and any co-authors
3. **Cover Image** - High-quality book cover image (JPG/PNG format)
4. **Book Description** - A compelling 2-3 paragraph overview of the book
5. **Publication Status** - Either "Available Now!" or "Forthcoming [Month, Year]"

### Purchase Information (Required for Published Books)
- **Amazon Link** - Direct link to Amazon product page
- **Barnes & Noble Link** - Direct link to B&N product page
- **Other Seller Links** - Any additional retailers (e.g., Shroff Publishers for international)

## Optional Book Information

### Detailed Content
- **Extended Description** - More detailed information about the book's contents
- **What You'll Learn** - Bulleted list of key learning outcomes
- **Target Audience** - Who should read this book
- **Table of Contents** - Complete chapter and section listing
- **Page Count** - Total number of pages
- **ISBN** - International Standard Book Number
- **Edition** - Edition number if applicable

### Supporting Materials
- **Downloads** - Links to companion files, source code, etc.
- **Errata** - List of corrections (page, original text, corrected text)
- **Reviews** - Customer testimonials and professional reviews

### Author Information
- **Author Bio** - Professional background and expertise
- **Author Photo** - Professional headshot
- **Contact Information** - Email, LinkedIn, website

## Preferred Data Input Format

### Option 1: JSON Format (Recommended)
This format is easiest for automated processing and ensures all fields are properly structured.

```json
{
  "title": "Book Title Here",
  "author": "Author Name",
  "filename": "book-title-here.html",
  "cover_image": "images/book-cover.jpg",
  "description": "Main book description...",
  "status": "Available Now!",
  "purchase_links": {
    "amazon": "https://amazon.com/...",
    "barnes_noble": "https://barnesandnoble.com/...",
    "other": [
      {
        "name": "Shroff Publishers",
        "url": "https://shroffpublishers.com/...",
        "region": "India and surrounding countries"
      }
    ]
  },
  "details": {
    "extended_description": "Detailed description...",
    "what_youll_learn": [
      "Learning outcome 1",
      "Learning outcome 2"
    ],
    "target_audience": [
      "Senior Java developers",
      "Software architects"
    ],
    "page_count": 420,
    "isbn": "978-0972954884",
    "edition": "Second Edition"
  },
  "table_of_contents": [
    {
      "section": "Section I: Planning",
      "chapters": [
        {
          "number": 1,
          "title": "Chapter Title",
          "topics": ["Topic 1", "Topic 2"]
        }
      ]
    }
  ],
  "resources": {
    "downloads": [
      {
        "title": "Source Code Examples",
        "url": "docs/examples.zip"
      }
    ]
  },
  "errata": [
    {
      "location": "Page 35",
      "original": "Original text",
      "corrected": "Corrected text"
    }
  ],
  "reviews": [
    {
      "text": "Review text...",
      "reviewer": "Reviewer Name",
      "title": "Reviewer Title/Company"
    }
  ],
  "author": {
    "name": "Author Name",
    "bio": "Author biography...",
    "photo": "images/author-photo.jpg",
    "email": "author@example.com",
    "linkedin": "https://linkedin.com/in/author",
    "website": "https://authorwebsite.com"
  }
}
```

### Option 2: Markdown Format
A simpler format for basic book entries:

```markdown
# Book Title

**Author:** Author Name
**Status:** Available Now!
**Cover:** images/book-cover.jpg

## Description
Main book description paragraph 1...

Main book description paragraph 2...

## Purchase Links
- [Amazon](https://amazon.com/...)
- [Barnes & Noble](https://barnesandnoble.com/...)
- [Shroff Publishers (India)](https://shroffpublishers.com/...)

## Details
### What You'll Learn
- Learning outcome 1
- Learning outcome 2

### Who This Book Is For
- Target audience 1
- Target audience 2

## Table of Contents
### Section I: Title
1. Chapter 1: Title
   - Topic 1
   - Topic 2
```

### Option 3: YAML Format
Structured but human-readable:

```yaml
title: Book Title Here
author: Author Name
filename: book-title-here.html
cover_image: images/book-cover.jpg
description: |
  Main book description paragraph 1...
  
  Main book description paragraph 2...
status: Available Now!

purchase_links:
  amazon: https://amazon.com/...
  barnes_noble: https://barnesandnoble.com/...
  other:
    - name: Shroff Publishers
      url: https://shroffpublishers.com/...
      region: India and surrounding countries

details:
  what_youll_learn:
    - Learning outcome 1
    - Learning outcome 2
  target_audience:
    - Senior Java developers
    - Software architects
  page_count: 420
  isbn: 978-0972954884
```

## File Requirements

### Images
- **Cover Image**: 
  - Format: JPG or PNG
  - Recommended size: 300x450px minimum
  - Location: Place in `site/images/` directory
  - Naming: Use descriptive name like `book-title-cover.jpg`

- **Author Photo** (if provided):
  - Format: JPG or PNG
  - Recommended size: 200x200px minimum
  - Location: Place in `site/images/` directory

### Supporting Files
- **Downloads**: Place in `site/docs/` directory
- **File naming**: Use descriptive names with version numbers

## Integration Steps

Once book data is provided:
1. Create new HTML file in `site/` directory
2. Add navigation menu entry
3. Copy images to `site/images/`
4. Copy any downloads to `site/docs/`
5. Update home page if featuring new book
6. Test all links and navigation

## Navigation Menu Update
Add entry to navigation in all HTML files:
```html
<li><a href="new-book-title.html">New Book Title</a></li>
```

## Recommended JSON Format
**The JSON format (Option 1) is recommended** because it:
- Ensures all data is properly structured
- Makes automated processing easier
- Reduces errors in data entry
- Can be validated against a schema
- Supports complex nested structures easily

Provide the book information in any of these formats, and it can be transformed into the appropriate HTML structure for the website.