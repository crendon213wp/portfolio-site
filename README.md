# Cisco Rendon — Portfolio Site

**Portfolio Site** · Built with the **ACAI Framework**

**Web Developer & Digital Systems Specialist**

A responsive, multi-page professional portfolio showcasing frontend development, WordPress solutions, HTML email development, and digital systems expertise. **Cisco Rendon** is the professional brand, **Portfolio Site** is the website and repository name, and **ACAI Framework** is the technical foundation. The site pairs a restrained, high-contrast visual direction with a lightweight, maintainable frontend build system.

> **Project status:** Active portfolio, preparing for the `v1.0.0` release. Project descriptions and measurable outcomes will continue to evolve as work is completed and verified.

## Purpose

Cisco Rendon — Portfolio Site is both a professional portfolio and a demonstration of frontend implementation practices. It is designed to help recruiters, hiring managers, and prospective collaborators quickly understand the work, explore selected projects, and make contact—without requiring them to read extensive technical documentation.

**Design principles:** mobile-first composition; separate mobile and desktop/tablet presentations where useful; semantic markup; responsive imagery; clear typography; modular source files; and progressive enhancement.

## Pages

| Route | Purpose |
| --- | --- |
| `index.html` | Home: professional introduction, hero presentation, and areas of expertise. |
| `about.html` | About: background, journey, and approach to digital work. |
| `work.html` | Work: selected projects and practical implementations. |
| `skills.html` | Skills / Expertise: capabilities in development, email, automation, and technical support. |
| `contact.html` | Contact: email call to action, services, and social links. |

The site intentionally uses distinct responsive layouts in some sections. Where the same heading appears in both layouts, the inactive presentation should remain hidden at its breakpoint so users encounter only the appropriate version.

## Selected work and capabilities

The portfolio highlights work including:

- **ACAI Framework:** a lightweight, reusable frontend starter and build workflow.
- **Responsive HTML email development:** layouts and templates designed for diverse email clients and screen sizes.
- **Offline UTM Builder:** a local utility for assembling campaign tracking URLs.
- **Stripo Local Dev Kit:** a community-developed workflow helper for working with the Stripo editor/plugin; not an official Stripo product.
- **Frontend and WordPress work:** responsive sites, component-based implementation, and practical website maintenance.
- **Digital systems and automation:** tools and workflows intended to reduce repetitive work and improve operational consistency.

Project descriptions focus on demonstrable work. Metrics are included only when measured and supportable; the site does not invent performance gains or business outcomes.

## Technology stack

| Layer | Technology | Role |
| --- | --- | --- |
| Markup | HTML5 | Semantic multi-page content |
| Layout | Bootstrap 5 via CDN | Responsive grid, utilities, and navigation components |
| Styling | Sass / SCSS | Modular styling, tokens, responsive typography |
| Icons | Font Awesome via CDN | Interface and social icons |
| JavaScript | Native JavaScript | Scroll interaction and progressive enhancement |
| JavaScript utility | jQuery via CDN | Small compatibility and DOM utilities |
| Build orchestration | Gulp 5 | Build tasks and file watching |
| HTML assembly | `gulp-file-include` | Shared partials and page composition |
| CSS optimization | `gulp-sass`, `gulp-clean-css`, `gulp-sourcemaps` | Compile, minify, and map styles |
| JS optimization | `gulp-terser`, `gulp-sourcemaps` | Minify and map scripts |
| HTML optimization | `gulp-htmlmin` | Minify generated pages |
| Images | `gulp-imagemin` | Optimize copied assets |
| Local preview | BrowserSync | Development server and live updates |
| Discovery | `gulp-sitemap`, `robots.txt` | Generate and expose crawl resources |

The published HTML examined for this documentation loads **Bootstrap 5.3.8**, **Font Awesome 7.0.1**, and **jQuery 3.7.1** through CDNs. Dependencies and CDN versions may change over time.

## Project structure

The **published output** follows this structure:

```text
portfolio-site/
├── index.html
├── about.html
├── work.html
├── skills.html
├── contact.html
├── css/
│   ├── application.css
│   └── application.css.map
├── js/
│   ├── app.js
│   └── app.js.map
├── images/
│   ├── favicon.svg
│   ├── home-hero.png
│   ├── hero-workspace.png
│   ├── work-hero.png
│   ├── contact-hero.png
│   └── ...additional portfolio and project images
├── robots.txt
└── sitemap.xml
```

The **development structure** below describes the ACAI/Gulp source organization. Refer to the `main` branch for the current file inventory:

```text
portfolio-site/
├── src/
│   ├── index.html
│   ├── about.html
│   ├── work.html
│   ├── skills.html
│   ├── contact.html
│   ├── partials/
│   │   ├── head.html
│   │   ├── head/
│   │   │   └── ...metadata, fonts, styles, social tags
│   │   ├── navbar.html
│   │   ├── footer.html
│   │   └── ...page-specific section partials
│   ├── scss/
│   │   ├── application.scss
│   │   ├── abstracts/
│   │   ├── base/
│   │   └── ...page and component styles
│   ├── js/
│   │   └── app.js
│   ├── images/
│   └── robots.txt
├── dist/                 # Generated site; not the editable source
├── site.config.js        # Shared site, social, and sitemap configuration
├── gulpfile.js           # Compilation, optimization, preview, and watches
├── package.json
└── README.md
```

### HTML partials

Pages are assembled from reusable HTML fragments using `gulp-file-include`. The shared partial system includes the document head, metadata and font links, navigation, footer, and page-specific sections. This allows common UI and SEO elements to be maintained in one place.

Sections developed for the portfolio include:

| Page | Section groups |
| --- | --- |
| Home | Responsive hero, introductory content, and expertise/features grid |
| About | Introduction, workspace imagery, professional journey, and supporting narrative |
| Work | Project hero and selected project presentations |
| Skills | Expertise and capability sections with supporting images |
| Contact | `contact-intro`, `contact-email`, `contact-services`, `contact-social` |

Example include syntax:

```html
@@include('partials/navbar.html')
```

The include path is illustrative; it must match the actual source file location and the including file's directory.

### Sass architecture

Styles are authored in modular SCSS and compiled into `css/application.css`. The architecture separates reusable concerns from page-level styling:

- **Abstracts:** design tokens, variables, spacing, and shared Sass utilities.
- **Base:** resets, typography, and foundational element styles.
- **Components and layout:** reusable interface patterns and structural styling.
- **Page partials:** styles scoped to specific portfolio sections.

The Contact page includes dedicated styles for its intro, email, services, and social sections (for example, `_contact-intro.scss`, `_contact-email.scss`, `_contact-services.scss`, and `_contact-social.scss`). Other page styles follow the same modular approach; consult the development source for their exact filenames.

The project uses a high-contrast palette, responsive type scales, Bootstrap breakpoints, and carefully controlled imagery. Layouts are designed mobile-first, with desktop/tablet variations where the composition benefits from them.

### Typography

Four Google Fonts are available through the shared font-loading partial:

| Font | Intended use |
| --- | --- |
| Space Grotesk | Brand and expressive display typography |
| Merriweather | Reading-oriented body copy |
| Montserrat | Interface and supporting text |
| Barlow | Labels, accents, and alternate typography |

Font roles and responsive sizes are centralized in Sass. Individual sections may select a different role where the design calls for it. The source typography partial is the authority for current variable mappings; the compiled stylesheet is the deployed result.

Responsive type can be expressed using CSS `clamp()` values:

```scss
$h1-font: clamp(3rem, 2.5385rem + 2.0513vw, 4rem);
$p-font: clamp(1rem, 0.8846rem + 0.5128vw, 1.25rem);
```

These are examples from the ACAI starter; check the current source tokens before treating them as the portfolio's final values.

## JavaScript behavior

The application JavaScript includes the following behaviors:

1. **jQuery compatibility:** calls `jQuery.noConflict()` so `$` can be released for other libraries.
2. **Copyright year:** writes the current year to `#current-year` when jQuery is available.
3. **Scroll reveals:** observes `main section` elements and animates opacity and vertical position as sections enter or leave the viewport.
4. **Reduced-motion support:** skips the scroll animation setup when `prefers-reduced-motion: reduce` is active at initialization.
5. **Keyboard-input detection:** distinguishes keyboard navigation from pointer interaction to support appropriate focus treatment.
6. **Contact email dialog:** offers Gmail, Outlook, the default email application, and copy-email options.

The scroll interactions use the native `IntersectionObserver` API rather than a large animation library. JavaScript is an enhancement to the underlying content, not a substitute for semantic HTML.

**Maintenance note:** the current published script checks reduced-motion preference at initialization; if live preference changes need to be supported, that behavior can be enhanced separately. Keep `noConflict()`, the copyright updater, and keyboard handling intact when revising the script.

## Gulp build workflow

The documented Gulpfile uses a single default workflow:

```bash
npx gulp
```

On startup, the build:

1. Cleans the generated `dist/` contents.
2. Expands HTML includes and minifies HTML.
3. Compiles Sass, minifies CSS, and writes source maps.
4. Minifies project JavaScript and writes source maps.
5. Optimizes images.
6. Copies `robots.txt`.
7. Generates `sitemap.xml` from built HTML pages.
8. Starts BrowserSync and watches source files.

The previously shared Gulpfile also exposes a full build task:

```bash
npx gulp build
```

**Current watcher behavior:** source changes trigger category-specific rebuilds. The originally supplied Gulpfile cleans all of `dist/` on startup, **not on every save**, so renamed or deleted files can leave stale outputs unless cleanup logic is added. A proposed targeted-cleanup revision was discussed, but a fully incremental watcher was **not confirmed as implemented**. This README intentionally does not claim otherwise.

### Source maps and generated files

`application.css.map` and `app.js.map` are generated alongside the minified files. The compiled CSS/JS in the published repository are deployment artifacts; edit the SCSS and unminified JavaScript in `src/`, then let Gulp regenerate the output.

## Site configuration

`site.config.js` centralizes values used by the HTML assembly and sitemap tasks. The shared Gulpfile reads `site.site`, `site.og`, and `site.seo`.

**Illustrative structure** (replace example values with the actual deployment settings):

```javascript
module.exports = {
    site: {
        title: "Cisco Rendon | Web Developer & Digital Systems Specialist",
        url: "https://YOUR-PUBLISHED-DOMAIN.example",
        author: "Cisco Rendon",
        description: "Portfolio of web development, HTML email, WordPress, and digital systems work.",
        language: "en",
        locale: "en_US"
    },
    og: {
        siteName: "Cisco Rendon | Portfolio",
        image: "https://YOUR-PUBLISHED-DOMAIN.example/images/YOUR-OG-IMAGE.png",
        imageAlt: "Cisco Rendon portfolio preview"
    },
    seo: {
        changefreq: "weekly",
        priority: 1.0
    }
};
```

The exact object keys expected by each HTML head partial should be checked against the current development source. This example documents the intended configuration shape; it is **not** a transcription of an inspected `site.config.js` file.

### SEO and social metadata

The generated HTML contains document titles, meta descriptions, robots directives, canonical metadata, Open Graph tags, favicon references, and shared fonts/styles. The generated sitemap uses the configured site URL.

**Production URL:** `https://crendon213wp.github.io/portfolio-site/`. Verify that canonical URLs, sitemap, `robots.txt`, and Open Graph metadata match the published URL after each deployment.

## Requirements and installation

- Node.js **20.19.0 or newer**, per the ACAI starter's documented requirement.
- npm.
- The **development-source repository** containing `package.json`, `gulpfile.js`, `site.config.js`, and `src/`.

The `gh-pages` branch contains the compiled static site. For local development and rebuilding, use the `main` branch, which contains the source files and build configuration.

For a local source checkout:

```bash
npm install
npx gulp
```

Run these commands from the folder containing `package.json` and `gulpfile.js`. BrowserSync serves the generated `dist/` directory and refreshes the browser during development.

## Deployment

Publish the generated static output (`dist/`) to the `gh-pages` branch (repository root). Keep editable source files on `main`. GitHub Pages serves the site at `https://crendon213wp.github.io/portfolio-site/`. PHP or a database server is not required.

Deployment checklist:

- Confirm the intended domain and page URLs in `site.config.js`.
- Verify page titles, descriptions, canonical tags, and Open Graph image URLs.
- Rebuild the site and check `sitemap.xml` and `robots.txt`.
- Verify image paths, navigation, email links, and social links.
- Test mobile, tablet, and desktop layouts, including the alternate hero compositions.
- Check keyboard navigation, focus visibility, image alternatives, and reduced-motion behavior.
- Review browser console errors and run performance/accessibility checks on the deployed site.

## Design and engineering philosophy

Portfolio Site follows the ACAI approach: **small, understandable tools; reusable components; and control over the generated output**. It favors a CDN-first stack, Sass modules, straightforward JavaScript, and transparent Gulp tasks over unnecessary abstraction or autonomous code generation.

The portfolio is intentionally concise. The Home page establishes identity, the Work page provides evidence, and the remaining pages supply context and a path to contact. Technical detail is available through the implementation and project links without overwhelming a recruiter-facing experience.

## Project naming and framework attribution

- **Professional brand:** Cisco Rendon
- **Public-facing project name:** Cisco Rendon — Portfolio Site
- **Repository:** `portfolio-site`
- **Technical foundation:** ACAI Framework

Built using the **ACAI Framework**, a lightweight frontend starter created by Cisco Rendon.

- ACAI Framework: https://github.com/crendon213wp/acai-framework
- Portfolio Site repository (`portfolio-site`): https://github.com/crendon213wp/portfolio-site

Portfolio Site is a personal portfolio implementation built on the ACAI Framework. The repository is named `portfolio-site`.

## License

The ACAI starter boilerplate states an **MIT License**. Verify the license file and intended licensing terms for **Portfolio Site** before treating the portfolio's content, original imagery, and personal branding as MIT-licensed. The starter's license does not automatically settle rights to every asset used in the portfolio.

## Author

**Cisco Rendon**

Web Developer & Digital Systems Specialist

Frontend Development · WordPress · HTML Email Development · Systems & Automation

**Portfolio:** Cisco Rendon — Portfolio Site

**Repository:** `portfolio-site`

**Started:** 2026

**Documentation updated:** October 2026
