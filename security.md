# Security Notes

## About This Project

Portfolio Site is a static, multi-page professional website built using the ACAI Framework, a lightweight frontend development workflow powered by Gulp.

The website does not provide:

- A backend or API
- A database
- User accounts or authentication
- A payment system
- A secret-management service

Security remains important. The website, its dependencies, content, and hosting configuration must be maintained responsibly.

## Keep Secrets Private

Never include passwords, API keys, access tokens, private certificates, or other sensitive credentials in files inside `src/`.

Anything included in public HTML, CSS, JavaScript, images, or configuration files may be accessible to website visitors.

Local environment files should be excluded from Git using `.gitignore`:

```text
.env
.env.*
!.env.example
```

The current frontend build does not require environment variables for normal operation.

An ignored file is not a complete security solution. Always review files before committing or publishing them.

## Dependencies

Portfolio Site uses npm dependencies for its Gulp build workflow.

Keep `package.json` and `package-lock.json` together.

For reproducible installations, use:

```bash
npm ci
```

Use `npm install` when intentionally updating dependencies.

Periodically review dependencies:

```bash
npm audit
npm outdated
```

Review reported vulnerabilities before applying updates.

After modifying dependencies, rebuild the website and verify that the generated files function correctly.

## Third-Party Assets

Portfolio Site uses external frontend resources, including Bootstrap, Font Awesome, jQuery, and Google Fonts.

To reduce potential security and availability risks:

- Use versioned CDN resources whenever possible.
- Verify package sources before updating dependencies.
- Remove unused external libraries.
- Review privacy considerations associated with third-party requests.
- Consider self-hosting important assets when appropriate.
- Use Subresource Integrity (`integrity` and `crossorigin`) when supported and appropriate.

Third-party services should be reviewed periodically for changes affecting security, privacy, or availability.

## Development Environment

Portfolio Site uses Gulp and BrowserSync for local development.

The development workflow generates the production website inside the `dist/` directory.

BrowserSync is intended for development and should not be used as a production web server.

The published website is hosted through GitHub Pages.

## Build and Deployment

The repository uses two primary branches:

- `main` — Development source code and build configuration.
- `gh-pages` — Compiled website served by GitHub Pages.

Before publishing:

1. Run the Gulp build from the project directory.
2. Review the generated files inside `dist/`.
3. Confirm that no credentials, private notes, or development-only files are included.
4. Verify the production URL in `site.config.js`.
5. Confirm the generated sitemap and metadata reference the correct domain.
6. Publish the compiled website to `gh-pages`.
7. Verify that the deployed website loads through HTTPS.
8. Test navigation, JavaScript functionality, and external resources.

### Production URL

`https://crendon213wp.github.io/portfolio-site/`

GitHub Pages provides HTTPS hosting. However, the project does not directly control all server-level security headers.

Security headers such as Content Security Policy, `Referrer-Policy`, and `X-Content-Type-Options` should be evaluated within the limitations of the hosting environment.

## Frontend Security

Portfolio Site uses HTML, SCSS, native JavaScript, and selected third-party libraries.

Follow these practices:

- Treat externally supplied content as untrusted.
- Avoid inserting untrusted content using `innerHTML`.
- Prefer `textContent` when displaying plain text.
- Validate and sanitize dynamic content where applicable.
- Keep third-party JavaScript dependencies to the minimum necessary.
- Avoid exposing sensitive information through client-side scripts.

### Contact Email Functionality

The Contact page provides an email selection dialog that allows visitors to:

- Open Gmail.
- Open Outlook.
- Use their default email application.
- Copy the public contact email address.

The dialog operates entirely within the browser.

It does not collect, process, or store visitor messages on the portfolio website.

Email communication is handled by the visitor's selected email provider or application.

The publicly displayed contact email address is intentionally available to visitors.

## Privacy and External Services

The website may load resources from third-party services.

Visitors who select an external email provider leave the portfolio's environment and interact with that provider's services.

Any analytics, external scripts, or additional integrations should be reviewed for applicable privacy and disclosure requirements.

## Reporting a Security Problem

Security concerns should be reported privately to the project maintainer before public disclosure.

A useful report should include:

- The affected page, file, or dependency.
- Steps required to reproduce the issue.
- The potential security impact.
- Suggested remediation, when available.

Never include passwords, private keys, access tokens, or other live credentials in a security report.

## Final Reminder

Portfolio Site is a static frontend implementation built using the ACAI Framework.

The framework provides a lightweight development foundation, but it does not replace responsible dependency management, secure hosting, or ongoing security reviews.

Security should be considered during development, deployment, and maintenance.

---

**Project:** Cisco Rendon — Portfolio Site  
**Repository:** `portfolio-site`  
**Technical Foundation:** ACAI Framework  
**Hosting:** GitHub Pages  
**Documentation Updated:** October 2026
