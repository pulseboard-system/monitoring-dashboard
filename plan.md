# Pulseboard implementation and design plan

## Product and material scope

Build a polished, fully clickable client-facing sales demonstration for a mobile-app feedback consultancy. It follows the user's actual workflow: collect feedback, categorize reviews, recognize recurring issues and trends, plan reproduction or solution-validation tests, and produce a monthly client report with research-backed recommendations and brand checks.

The recommended deliverable is an honest demo, not a claim of 70–80 live connections. Include a catalog of 78 named platform options covering Apple App Store, Google Play, mobile support tickets, Jira, TestFlight, in-app surveys and more. Demo connections and sync are visibly labelled simulated. Real OAuth, polling, webhooks and secret handling are a separate production implementation requiring individual providers' access and permissions. Static Cloudflare Pages cannot safely hold platform secrets. No client account, credentials, real customer data or API secrets are required for the demo.

## Implementation

React + TypeScript + Vite, deployed as a static site with no Manus runtime dependency. State persists in localStorage in the current browser and can be reset for sales calls. A realistic fictional mobile app and dataset anchor the demo; clear demo indicators remain visible. The demo data and categories are editable; imports support normalized CSV feedback. No server, database, paid AI endpoint or authentication gate is needed. Classification is deterministic and user-correctable, not falsely presented as live AI. Insights and monthly summaries derive from the current data. Public sources are curated references, not an autonomous live research engine.

Core screens:
1. Overview: KPI cards, feedback volume and sentiment charts, source breakdown, priority themes, and recent feedback. Date-range and source filters update visible data.
2. Feedback inbox: searchable and filterable records, selection and bulk actions, detail drawer, editable category/priority/status and analyst notes, CSV export/import and deterministic classification.
3. Trends: recurring themes with severity, counts, change indicators and related feedback. Turn an issue into a test scenario or recommendation.
4. Testing lab: create/edit reproduction and validation scenarios, device/build/preconditions, steps and expected results, assign status and record outcomes.
5. Recommendations: prioritized action items linked to feedback themes, testing evidence, external best-practice references, and editable example brand-guideline checks.
6. Research library: curated official mobile UX/accessibility references plus clearly labelled sample client brand guidelines. Add custom sources and brand rules; link evidence to recommendations. No claim of complete brand validation without the client's actual guidelines.
7. Monthly reports: select month, regenerate a deterministic data summary, edit narrative, include recommendations and citations, save reports, export Markdown and print/save as PDF with a clean print stylesheet.
8. Integrations: search/filter a catalog of 78 platforms; inspect connection metadata, simulate connect/disconnect/sync, and explain production requirements without asking for secrets.
9. Workspace settings: edit fictional client/app names, customize demo preferences, export/import workspace JSON, and reset sample data.

All navigation, primary actions, drawers, modal forms and exports must function. The app should work on desktop for Zoom and adapt to smaller screens. Clearly distinguish local demo persistence from a multi-user production database.

## Project structure

- `src/app/`: shell, navigation, context and persistent workspace state.
- `src/components/`: shared controls, badges, icons, drawers and charts.
- `src/pages/`: overview, inbox, trends, testing, recommendations, research, reports, integrations and settings.
- `src/data/`: realistic seed feedback, connector catalog and verified research references.
- `src/lib/`: date/filter/aggregation, import/export and report utilities.
- `src/styles/`: tokens, layout, component and print styling.
- `public/`: local brand mark, favicon, SPA redirects and route manifest.
- `README.md`: setup, Cloudflare Pages build settings, sales-call walkthrough, demo limitations and production integration roadmap.
- Source ZIP and built-static ZIP are supplied for GitHub/Cloudflare delivery.

## Design alternatives

- Quiet editorial SaaS workspace with moss accents and warm ivory surfaces (probability 0.07).
- Midnight technical operations console with electric lime signals (probability 0.04).
- Swiss information design with cobalt and compact typography (probability 0.06).

Chosen direction: quiet editorial SaaS workspace.

### Design Movement
Contemporary editorial product design with restrained Swiss information hierarchy.

### Core Principles
Readable at Zoom screen-sharing scale; purposeful density; calm surfaces with clear operational signals; progressive disclosure rather than an overwhelming wall of controls.

### Color Philosophy
Warm off-white canvas, white working surfaces, charcoal text and a distinctive moss-green accent communicate clarity and trustworthy analysis. Green, amber and coral communicate sentiment and severity without relying on color alone.

### Layout Paradigm
Fixed narrow sidebar, spacious topbar, asymmetrical working canvas with broad main insight area and a narrower actionable context rail. Data lists and report pages provide clear reading flow rather than centralized decorative grids.

### Signature Elements
A compact waveform logomark, rounded-square source monograms, and understated capsule badges. Fine separators and lightly tinted insight panels distinguish context without heavy shadows.

### Interaction Philosophy
Every click advances a plausible consultancy workflow. Drawers preserve context; visible filters and dismissible confirmations make changes understandable. No fake backend success messages.

### Animation
Fast 140–180ms hover and focus transitions. Drawers fade/slide subtly. Charts avoid prolonged introductions. Respect reduced-motion preferences.

### Typography System
Use a locally served or securely referenced modern sans-serif such as Inter for working UI; strong 28–34px page headings, 13–14px table text, tabular numeric metrics, and small uppercase metadata labels with modest tracking.

### Brand Essence
Pulseboard turns scattered mobile feedback into evidence-led product decisions. Calm, precise, useful.

### Brand Voice
Direct analyst language with specific outcomes. Examples: “Know what needs your attention.” and “Turn this issue into a test scenario.”

### Wordmark & Logo
Custom inline waveform mark inside a moss rounded square paired with a tightly tracked lowercase pulseboard wordmark. Implement as an SVG to remain portable without decorative imagery.

### Signature Brand Color
Moss green `#4D6B4A`, used sparingly for the active navigation, key actions, chart focus and the brand mark.

## Approval

Proposed for user approval before implementation. The alternative of actual live ingestion requires a separate provider and backend discovery scope.
