# NeuByte Router — Organization Redirect Hub
The **NeuByte Router** is a lightweight static site that provides clean, memorable URLs for navigating key Discussions, documents, and resources across the NeuByte Technologies GitHub Organization.

Instead of sharing long GitHub URLs, the router offers short, stable, branded links such as:

Code
---
router.neubyte.com/discussions/4
router.neubyte.com/discussions/5
---

This improves navigation, consistency, and cross‑repo integration across the NeuByte ecosystem.

# Purpose
The router exists to:
- Provide **short, human‑friendly URLs** for GitHub Discussions
- Serve as a **central navigation hub** for the NeuByte portfolio
- Support SDLC documentation, portfolio series, and multi‑sprint planning
- Allow future expansion into redirects for repos, docs, and architecture pages

It is intentionally simple, stable, and easy to maintain.

# Current Discussion Redirects
The router currently maps the following Discussions:

| Router Path | Discussion Title | GitHub Discussion # |
| --- | --- | --- |
| ``/discussions/3`` | Welcome to the SDLC Portfolio Series | #3 |
| ``/discussions/4`` | Sprint 4B — Plan | #4 |
| ``/discussions/5`` | NeuByte Roadmap — Multi‑Sprint Plan | #5 |
| ``/discussions/6`` | LinkedIn Portfolio Series — Public Hub | #6 |

Each path performs a simple HTTP redirect to the corresponding GitHub Discussion.

# Architecture Overview
The router is a static site built with:
- **HTML redirect pages**
- **NeuByte Design System** (Manrope, spacing, minimal layout)
- **GitHub Pages** for hosting
- **CNAME** for custom domain routing

Each redirect page uses a minimal HTML template:

html
---
<meta http-equiv="refresh" content="0; url=https://github.com/NeuByteTechnologies/...">
---

This ensures fast, reliable navigation with no backend dependencies.

# Repository Structure

Code
---
/
├── discussions/
│   ├── 3.html
│   ├── 4.html
│   ├── 5.html
│   └── 6.html
├── assets/
├── index.html
└── CNAME
---

- discussions/ contains one redirect page per GitHub Discussion
- index.html provides a landing page with links to all redirects
- CNAME binds the router to router.neubyte.com

# Adding a New Redirect
To add a new Discussion redirect:

Create a new HTML file under ``/discussions/``  
Example: ``7.html``

Add a redirect tag:

html
---
<meta http-equiv="refresh" content="0; url=https://github.com/NeuByteTechnologies/.../discussions/7">
---

Update ``index.html`` to include the new link

Commit + push to ``main``

GitHub Pages will deploy automatically

Redirects are live within seconds.

# Deployment
The router is deployed automatically via **GitHub Pages**.

Any push to ``main`` triggers:

- Jekyll build
- Static site deployment
- Redirect updates

No manual steps required.

# Future Enhancements
The router is designed to expand as the organization grows. Planned additions include:

- Redirects for architecture diagrams
- Redirects for standards documentation
- Redirects for portfolio modules
- Redirects for Fitness App help articles
- Redirects for API documentation
- Redirects for multi‑repo navigation

This keeps NeuByte navigation clean and centralized.

# Contact
For questions or updates to router paths:
**gordon.neuls@gmail.com**
