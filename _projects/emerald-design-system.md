---
title: Emerald Design System
company: Stone – Mundipagg (Pagar.me)
cover: /assets/images/emerald-design-system/emeraldinho.png
cover_alt: Emerald`s mascot
year: 2018–2021
role: Front-end Designer / Technical Leader
responsibilities:
  - UX strategy and research
  - UI and visual design
  - Component library architecture
  - Documentation and adoption advocacy
timeline: 2018 – 2021
summary: A framework-agnostic design system in HTML, CSS and JavaScript, adopted across all products.
order: 1
links:
  - label: Patternlab
    url: https://stgworkbench.mundipagg.com/?p=apps-patternlab-home
  - label: Case presentation
    url: https://www.figma.com/proto/a3PV8gtRvb13froMNWuGma/Emerald-Case-Study?page-id=1%3A257&node-id=1-258&p=f&viewport=25%2C327%2C0.05&t=YLHne4eYrjBuCcvp-1&scaling=contain&content-scaling=fixed
---

I built Emerald to be an agnostic, framework-free design system, using HTML, CSS, and JavaScript. The components were used for UI testing on Patternlab, and later adapted by other teams into Vue.js, React, or Angular components.

Emerald was implemented across all products, including the landing page, and I focused on its continuous improvement, documentation, and adoption.

By building Emerald, I enabled cross-team scalability and faster delivery across different tech stacks, eliminated duplicate work, created visual consistency, and reduced development time.

## Context and challenge

- Rapid growth required multiple product teams, each of which reinvented UI specifications, tokens, spacing, and accessibility.
- No shared style guide: inconsistent buttons, forms, typography, and colors.
- High volume of UI bugs, slow design-to-dev handoffs, and frustrated engineers and clients.

## Research and discovery

- **Audit:** reviewed existing apps and cataloged UI inconsistencies.
- **Stakeholder interviews:** talked with PMs, engineers, and designers; validated pain points around scalability and brand fragmentation.
- **Benchmarking:** studied Bootstrap, Carbon (IBM), Primer (GitHub), and Swarm (Meetup) for best practices in design systems, theming, and tokens.

## Design and build process

### Token-based theming

- Defined core tokens (colors, spacing, typography scales) in JSON and CSS variables.
- Established light and dark modes with consistent feedback states (success, warning, danger, info).

### Atomic component library

- Adopted Patternlab and Atomic Design to create HTML, CSS, and JS-only components.
- Built a Storybook-style documentation site, exported as a static styleguide for all teams.

### Tooling and workflow

- Started the design library in Sketch (symbols and patterns), then migrated to Figma for live token syncing.
- Published an NPM package of compiled CSS and utilities, integrated via Git submodule in each front-end repo.
- Ran internal “office hours” workshops and created contribution guidelines on GitHub.

## Outcomes and metrics

- Faster design-to-dev handoff.
- Fewer UI inconsistencies.
- Fewer UI bugs reported by QA in each release.
- Adopted by front-end teams within 6 months.
- Increased developer and designer satisfaction; Emerald became the official UI foundation for the company’s products.

The Patternlab project is on a test environment and currently not in use, so it may have some bugs.


{% include image.html name="1.png" caption="Mundipagg’s landing page" %}
{% include image.html name="2.png" caption="Styleguide: Emerald’s documentation" %}
{% include image.html name="4.png" caption="Other UI assets built with Emerald" %}
{% include image.html name="5.png" caption="Other UI assets built with Emerald" %}
