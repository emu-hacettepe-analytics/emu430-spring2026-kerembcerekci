# Agent Guidelines for EMU430 Quarto Website

## Project Overview

This is a personal academic website for EMU430 Data Analytics course, built with [Quarto](https://quarto.org/). The site contains course assignments, a project page, and personal information for Kerem Berkalp Çerekçi.

## Build Commands

### Preview Site Locally
```bash
quarto preview
```
Runs a live preview server at `http://localhost:4200` with hot reloading.

### Render All Documents
```bash
quarto render
```
Renders all `.qmd` files to HTML in the `docs/` directory.

### Render a Single File
```bash
quarto render path/to/file.qmd
```
Example: `quarto render assignments/assignment-1.qmd`

### Check Document
```bash
quarto check
```
Validates the project configuration and checks for issues.

### Render to Specific Format
```bash
quarto render --to pdf    # Render to PDF
quarto render --to docx   # Render to Word
```

### Clean Build Artifacts
```bash
quarto preview --clean   # Clean before preview
rm -rf docs/_freeze/      # Remove cached outputs
```

## Code Style Guidelines

### General Principles
- Write clear, well-organized content with proper Markdown formatting
- Use semantic heading hierarchy (H1 for titles, H2 for main sections, H3+ for subsections)
- Keep code chunks focused and well-commented

### Quarto Document Structure
Every `.qmd` file should include YAML front matter:
```yaml
---
title: "Page Title"
---
```

### R Code Chunks
- Always label code chunks with descriptive names when they serve a specific purpose
- Use proper R coding conventions (spacing, naming with underscores)
- Include comments for non-obvious operations

Example:
```r
# Good
mean_value <- mean(data$column, na.rm = TRUE)

# Include AI assistance notes for significant contributions
# [AI prompt used: "..."]
```

### File Naming Conventions
- Use lowercase with hyphens for filenames: `assignment-1.qmd`, `my-post.qmd`
- Avoid special characters and spaces
- Directory names should be lowercase: `assignments/`, `posts/`

### Content Style
- Academic writing tone for assignments
- Personal but professional for about/posts pages
- Use proper Turkish diacritics (ç, ı, ö, ş, ü, ğ) in Turkish content
- Use proper English punctuation in English content

### Formatting
- Use `**bold**` for emphasis and important terms
- Use proper bullet points with `-` or `*`
- Include line breaks between sections for readability

## Project Structure

```
.
├── _quarto.yml          # Quarto website configuration
├── index.qmd            # Home page
├── about.qmd            # About page
├── posts.qmd            # Blog posts listing
├── assignments.qmd      # Assignments listing
├── assignments/
│   ├── assignment-1.qmd
│   └── assignment-2.qmd
├── project.qmd          # Course project page
├── styles.css           # Custom CSS styles
├── docs/                # Rendered HTML output (published to GitHub Pages)
└── .quarto/             # Quarto cache/build artifacts
```

## Workflow for Adding Content

### Creating a New Assignment
1. Create file: `assignments/assignment-N.qmd`
2. Add front matter with title
3. Write content with embedded R code
4. Run `quarto render assignments/assignment-N.qmd` to preview
5. The assignment listing will automatically update in `assignments.qmd`

### Creating a New Post
1. Create file in `posts/` directory: `posts/my-post.qmd`
2. Add front matter with title and date
3. Write content
4. Run `quarto render posts/my-post.qmd` to preview

## Configuration Reference

The `_quarto.yml` file controls:
- Website title and navigation
- Sidebar structure and search
- Theme (light: pulse, dark: superhero)
- Output directory (`docs/` for GitHub Pages)
- Table of contents settings

## GitHub Pages Deployment

The `docs/` directory is published via GitHub Pages. After rendering:
```bash
git add docs/
git commit -m "Update site content"
git push
```

## Important Notes

- Do not edit files in `docs/` directly - they are generated
- Do not edit files in `.quarto/` directory - these are cache files
- The `_site/` directory is for local preview only, do not commit
- Always run `quarto render` before committing to ensure HTML is up to date

## Editor Settings

The `editor: visual` setting in `_quarto.yml` enables the visual editor in Quarto. For text-based editing, you can set it to `source`.
