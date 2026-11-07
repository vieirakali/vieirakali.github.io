---
title: Dark mode for Black Friday
company: Hurb
year: 2024
role: Senior Product Designer
responsibilities:
  - Product design lead
  - Neutral color scale and tokens
  - Cross-team coordination
timeline: Oct – Nov 2024
summary: A neutral tone scale and dark mode across Hurb’s website and app for Black Friday 2024.
order: 5
---
I developed a neutral tone scale and implemented CSS for dark mode across Hurb’s website and app for Black Friday 2024.

- Aligned with Brand, Product, App, and Engineering teams to overcome technical challenges that had previously blocked implementation.
- Created a brand-aligned color palette, theme override stylesheet, and app UI layouts.
- Led Product Design efforts, coordinated cross-team reviews, and ensured consistency across Marketing, Web, and App.
- Presented the project in an internal launch video and highlighted contributions from all teams.
- The project was featured on Hurb’s official blog.

## Process

### Research

- Competitor analysis on top apps with dark mode.
- Interviews with users about their dark mode habits and use cases.
- Review of WCAG contrast ratios and common failure points.

### Audit

- Identified all light-theme-dependent color tokens and components.
- Flagged critical accessibility violations in existing mockups.

### Design system planning

- Defined color roles (surface, on-surface, accent, error) instead of fixed values.
- Created a neutral palette that adapts across light and dark themes.
- Implemented alias tokens and elevation logic for surfaces.

### Testing

- Tested readability in different environments: mobile, desktop, low light.
- Validated contrast levels with automated tools and real user feedback.

## Design decisions

- Built dual-theme support using token aliases.
- Designed elevation and depth with shadows and gradients instead of flat swaps.
- Avoided pure black (#000) and pure white (#fff) in favor of dark grey to reduce eye strain.
- Used transparency layers to maintain context across modals and side panels.
- Applied accessible variants for states like focus, selected, and hover.

## Outcome

- Launched full dark mode support for all core flows.
- Integrated it into the design system with clear documentation and tokens.
- Improved developer handoff through clear variable usage across themes.
- Received positive internal feedback.

<!--
  Exporte as telas do Figma para assets/img/hurb-dark-mode/ e descomente.

![Dark mode on mobile](/assets/img/hurb-dark-mode/mobile.png)
*Testing dark mode on mobile*

![Contrast and accessibility checks](/assets/img/hurb-dark-mode/contrast.png)
*Testing components, contrast and accessibility with Figma plugins*

![Dark mode home page](/assets/img/hurb-dark-mode/home.png)
*Dark mode applied to the home page*
-->
