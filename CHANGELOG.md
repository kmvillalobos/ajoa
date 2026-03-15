# Changelog

All notable changes to AstroDeck are documented in this file.

## [2.0.4] - 2026-03-15

### Added

- Changelog: latest release highlighted with larger pulsing timeline dot and "Latest" badge
- Hero version badge now links to `/changelog` page
- 5 new funny fictional blog posts (Unicorn Startup, Kraken Plumber, Centaur Delivery, Medusa Hairstylist, Yeti Ski Instructor)

### Changed

- Footer restructured into "AstroDeck" (Home, Docs, Sections, Changelog) and "Pages" (Blog, Content, Login) columns
- Changelog badges use semi-transparent foreground colors for dark mode visibility
- All changelog dates corrected to match actual GitHub release dates
- Blog post dates spread from November 2025 to March 2026

### Removed

- 5 real tutorial blog posts replaced with fictional examples
- "Built With" column removed from footer

## [2.0.3] - 2026-03-15

### Added

- Documentation page (`/docs`) with AI-first two-column layout — each task shown as AI prompt and manual steps
- 9 docs sections: Getting Started, Create Page, Add Section, Custom Component, Theme & Colors, Design Tokens, Blog Post, Build & Deploy, Project Structure
- Design Tokens reference table with all CSS custom properties and Tailwind utility mappings
- Mobile collapsible "On this page" sub-navigation for `/docs` and `/sections` pages
- Header navigation dropdown: Blog, Content, Login grouped under "Pages"
- Active page highlighting in main navigation (`aria-current="page"`)
- Responsive design checks added to AstroDeck agent and QA/UI-design skills

### Changed

- `/docs` and `/sections` use FullWidthLayout with consistent `px-6 md:px-12` padding
- Sidebar nav hover respects active state (no more unreadable text on hover)
- All cards and code blocks use `rounded-xl` per design system
- Touch targets increased to 44px minimum on nav links
- Scroll margin accounts for dual sticky bars on mobile (`scroll-mt-32 lg:scroll-mt-20`)

## [2.0.2] - 2026-03-15

### Added

- Self-improving skill system with 6 domain skills (ui-design, tailwind, astro, accessibility, qa, content-seo)
- `/launch-check` command for production-readiness checks across all skill KPIs
- Footer: "for templatedeck.com" link in creator section

### Fixed

- Title redundancy: "AstroDeck" no longer appears twice in `<title>` tag
- Inline styles replaced with Tailwind utilities (`z-0`, `z-10`)
- Hardcoded RGBA shadow replaced with themeable `shadow-primary/40`
- ESLint errors: empty interfaces, triple-slash reference
- TypeScript error in `rss.xml.ts`
- Section padding consistency (`py-32` → `py-20 px-6`)
- Card border-radius consistency (`rounded-lg` → `rounded-xl`)
- Heading font-weight hierarchy (`font-bold` → `font-semibold` for h3)
- External links: added `noreferrer` to `rel` attribute

---

## [2.0.1] - 2026-03-14

### Added

- Changelog page with timeline design at `/changelog`
- Changelog link in main navigation

---

## [2.0.0] - 2026-03-14

### Breaking Changes

- **Astro 6.0** - Upgraded from Astro 5.x to 6.0.4 (requires Vite 7)
- **Node.js 22+** - Minimum Node.js version raised from 18 to 22
- **@astrojs/react 5.0** - Upgraded from 4.x to 5.0.0

### Migration Guide

These changes are required when upgrading from v1.x:

1. **Update Node.js** to version 22 or higher
2. **Zod imports** - Change `import { z } from 'astro:content'` to `import { z } from 'astro/zod'`
3. **View Transitions** - Change `ViewTransitions` to `ClientRouter` from `astro:transitions`
4. Run `npm install` to update all dependencies

### Changed

- Migrated all layouts from `ViewTransitions` to `ClientRouter` (BaseLayout, FullWidthLayout, AuthLayout, MinimalLayout)
- Updated content config to import `z` from `astro/zod`
- Updated all documentation for Astro 6 (README, AGENTS.md, CONTRIBUTING.md, blog posts)
- Rewrote `/theme` command for OKLCH/Tailwind v4 (`--color-` prefix, `@theme` directive)
- Enhanced `/audit` command with Astro 6 deprecation checks
- Improved AstroDeck agent with tech stack context, migration checklist, and deprecated pattern detection
- Fixed AGENTS.md theme system docs from HSL to OKLCH format
- Updated CSS examples in blog posts from `:root` to `@theme` directive

### Dependency Updates

| Package | From | To |
|---------|------|-----|
| astro | ^5.16.6 | ^6.0.4 |
| @astrojs/react | ^4.4.2 | ^5.0.0 |
| @astrojs/sitemap | ^3.6.0 | ^3.7.1 |
| @astrojs/rss | ^4.0.14 | ^4.0.17 |

---

## [1.5.2] - 2025-12-28

### Fixed

- Refactored dark mode system and theme architecture
- Fixed TypeScript error with HTMLElement generic on querySelectorAll (TS2339)

## [1.5.1] - 2025-12-27

### Fixed

- Improved muted-foreground contrast in light mode
- Dark mode contrast improvements and theme persistence fix
- Updated cover.png for OG preview and README

## [1.5.0] - 2025-12-26

### Added

- Functional copy-code buttons to sections page with imports

### Changed

- Updated dependencies (Astro 5.16.15, security fixes)

### Fixed

- README download link and installation option numbering

## [1.4.0] - 2025-12-25

### Added

- Content Layer API migration for future Astro v6 compatibility

## [1.3.0] - 2025-12-24

### Added

- MinimalLayout for standalone pages (404, maintenance, landing)
- Comprehensive SEO support (OpenGraph, Twitter Cards, canonical URLs, sitemap, RSS)
- PROJECT.md for user-specific AI instructions
- Responsive header with hamburger menu
- MCP server documentation (Astro Docs, shadcn/ui)

### Fixed

- Handle undefined Astro.site in SEO component

### Changed

- Phase 2-4 improvements: content, pages, DX, code quality, performance

## [1.2.0] - 2025-12-22

### Added

- Claude Code AI Agent for project assistance
- AI tools grid with Gemini CLI and VS Code support
- Git workflow rules to AGENTS.md
- AI feature section on homepage

### Changed

- Consolidated AI guidelines into AGENTS.md standard
- Redesigned AI tools grid to match Features section style

## [1.1.0] - 2025-12-20

### Added

- AI-friendly development documentation (AGENTS.md)
- Vercel Analytics integration
- Comprehensive README documentation

### Changed

- Migrated to Tailwind CSS v4.1.18
- Redesigned features section with grid layout
- Updated footer with Pages, Built With, and Creator sections

## [1.0.0] - 2025-12-18

### Added

- Initial release
- Pre-built sections: Hero, CTA, Features, Pricing, Testimonials, Newsletter, LogoCloud
- Layouts: BaseLayout, FullWidthLayout, AuthLayout
- shadcn/ui components: Button, Card, Badge, Input, Label
- Dark mode with theme persistence
- Blog with Content Collections
- TypeScript support
- ESLint and Prettier configuration
