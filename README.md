# Tonalli v2

Tonalli is a lightweight, CDN-first frontend build pipeline with multi-page templating, SCSS design systems, and build-time SEO integration.

It is intentionally minimal, but no longer just a mockup tool.

Tonalli compiles, structures, and assembles complete static websites using a modular architecture without introducing heavy frameworks or runtime dependencies.

---

## Philosophy

- Mockups → Production-ready static builds  
- CDN over bundling  
- Build-time composition over runtime hacks  
- No framework lock-in  
- No runtime assumptions  
- Backend-agnostic  

Tonalli is not a framework.  
It is a frontend pipeline + templating system designed to stay out of your way while still enabling scalable architecture.

If a project grows, the compiled output can be migrated into:
- PHP
- Node
- Laravel
- WordPress
- Rails

…without refactoring the frontend.

---

## What Tonalli Does

- Compiles SCSS → CSS (with sourcemaps)
- Minifies HTML, CSS, and JavaScript
- Optimizes images
- Serves files locally via BrowserSync
- Watches for file changes during development
- Supports build-time HTML templating via partials
- Enables multi-page architecture with shared components
- Injects dynamic metadata and SEO content per page

---

## What Tonalli Does Not Do

- No React, Vue, or Angular
- No vendor bundling
- No framework transpilation
- No runtime templating (no fetch, no DOM injection)
- No opinionated frontend architecture

Frameworks and libraries should be loaded via CDN during development.

---

## Key Features (v2 Upgrade)

### Build-Time Templating

@@include('partials/navbar.html', { "active": "home" })

- Shared navigation and footer
- Dynamic page state (active links)
- Clean separation of layout and content

---

### Multi-Page Architecture

- index.html  
- about.html  
- projects.html  
- skills.html  
- contact.html  

Each page:
- Has unique metadata
- Shares layout components
- Compiles into static HTML

---

### Dynamic SEO + Metadata

@@include('partials/head.html', {
  "title": "Projects",
  "description": "Professional work and case studies."
})

- Dynamic <title>
- Unique meta descriptions
- Better search engine visibility

---

### JSON-LD Structured Data

- Person schema  
- WebSite schema  
- WebPage schema (dynamic per page)  

Improves:
- Search engine understanding
- Indexing quality
- Professional SEO signals

---

### SCSS Design System

- Typography using clamp()
- REM-based spacing system
- Centralized variables
- Reusable layout utilities

Example:

$h1-font: clamp(1.875rem, 0.4rem + 3vw, 4rem);

---

### UI Enhancements

- Smooth hover interactions
- Micro-transitions
- Consistent button states
- Active navigation states (build-time controlled)

---

## What Changed from v1

| Feature | v1 | v2 |
|--------|----|----|
| HTML structure | Static | Modular templating |
| Navigation | Duplicated | Shared partial |
| SEO | Basic | Dynamic + structured data |
| Styling | Basic SCSS | Design system |
| Page architecture | Single page | Multi-page |
| Runtime JS includes | Optional | Removed |
| Build pipeline | Asset-focused | Layout-aware |

---

## Requirements

- Node.js 18+
- npm
- Gulp CLI
- (Optional) nvm

Install Gulp CLI globally:

npm install -g gulp-cli

---

## Node Version Management

Tonalli includes an .nvmrc file:

18

If using nvm:

nvm install  
nvm use

---

## Setup

npm install  
gulp

This will:
- Clean the dist/ directory
- Compile HTML with includes
- Compile SCSS
- Minify JS
- Optimize images
- Start BrowserSync
- Watch for changes

---

## Project Structure

project-root/
├─ gulpfile.js
├─ package.json
├─ README.md
├─ .gitignore
├─ .nvmrc
│
├─ src/
│ ├─ pages/
│ │ ├─ index.html
│ │ ├─ about.html
│ │ ├─ projects.html
│ │ ├─ skills.html
│ │ └─ contact.html
│ │
│ ├─ partials/
│ │ ├─ head.html
│ │ ├─ navbar.html
│ │ └─ footer.html
│ │
│ ├─ scss/
│ │ └─ application.scss
│ │
│ ├─ js/
│ │ └─ app.js
│ │
│ └─ images/
│
└─ dist/
├─ index.html
├─ about.html
├─ projects.html
├─ skills.html
├─ contact.html
├─ css/
├─ js/
└─ images/

---

## Notes

- Only src/ files are processed  
- dist/ is disposable and rebuilt on each build  
- Vendor libraries should be included via CDN  
- Output is fully static and deployable anywhere  
- No runtime dependencies required  

---

## Version Control

.gitignore excludes:

- node_modules/  
- dist/  
- OS/editor artifacts  
- local environment files  

---

## Naming

Tonalli  
From Nahuatl: life force, inner energy, that which animates creation.

A tool designed to be:
- Simple
- Fast
- Intentional

---

## Version

Tonalli v2.0  
A lightweight frontend pipeline with modular architecture and build-time templating.

---

## Status

Tonalli v2 is stable and production-ready for:

- Portfolio sites  
- Landing pages  
- Static marketing sites  
- Frontend prototypes  

No framework lock-in.  
No unnecessary abstraction.  

---

## Why Autoprefixer Is Not Included

Tonalli does not include autoprefixer by default.

- Modern browsers no longer require most vendor prefixes  
- Tonalli prioritizes speed and simplicity  
- Can be added later if needed  

---

## Final Note

Tonalli is not trying to compete with frameworks.

It exists in a different space:

Fast, controlled, framework-free frontend development
