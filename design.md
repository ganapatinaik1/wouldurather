# Visual Redesign Specification — Would You Rather

design the application's frontend around a typography-led editorial gameboard aesthetic.

The result must look like a carefully art-directed independent internet product, not an AI-generated SaaS template.

## Art direction

Combine Swiss editorial graphic design, modern typography, restrained brutalist influence, and playful competitive internet culture.

The interface should feel precise, confident, clean, slightly irreverent, and highly usable.

Use flat, opaque surfaces and strong typographic hierarchy. Avoid rounded-card design, glassmorphism, blur effects, generic gradients, excessive shadows, decorative floating blobs, and repetitive dashboard layouts.

## Color tokens

- Background: #F4F1E9
- Primary text and dark surfaces: #191A18
- Primary interactive accent: #3155F5
- Secondary expressive accent: #E6533D
- Borders and separators: #D8D4CA
- Secondary text: a muted neutral chosen to maintain accessible contrast against each surface
- White or near-white: reserved for surfaces that genuinely need additional contrast

Use cobalt primarily for selected states, links, focus indicators, and interactive elements. Use vermilion sparingly. Do not distribute every accent color across every component.

Use accessible text contrast and explicit hover, focus, active, disabled, loading, and error states.

## Typography

- Display and headings: Archivo, with an appropriate fallback.
- Body and interface text: Inter, with an appropriate fallback.
- Scores, timestamps, percentages, and metadata: IBM Plex Mono, with an appropriate fallback.

Use expressive but controlled headline sizing, readable question text, consistent line heights, and restrained uppercase metadata.

Load fonts responsibly, preferably self-hosted when licensing permits. Define a consistent type scale and avoid arbitrary font sizes throughout the codebase.

## Geometry and layout

- Use square corners as the default: border-radius: 0.
- Use thin 1px borders and horizontal rules to structure content.
- Use spacing, alignment, and typography instead of shadows to create hierarchy.
- Establish a consistent spacing scale and responsive page gutters.
- Use a desktop layout with a compact navigation rail, central feed, and optional right sidebar.
- Use a single-column mobile layout with bottom navigation.
- Keep content widths readable and avoid oversized empty spaces.

Small circular avatars are allowed where they are semantically appropriate; this does not justify rounding the surrounding interface.

## Component requirements

### Home feed
- Typography-led question panels separated by thin rules.
- Clear author identity, timestamp, and reaction controls.
- Two unmistakable answer options.
- Legible vote percentages and flat progress bars.
- Compact comment previews and profile links.
- A subtle Hall of Fame teaser in the right sidebar on desktop and a compact entry point on mobile.

### Card mode
- One question at a time.
- Large, readable question text.
- Two strong rectangular answer buttons.
- A visually secondary but accessible Skip action.
- Immediate interaction feedback and a restrained transition between questions.

### Profiles
- Strong username heading and avatar.
- Prominent statistics without rounded statistic-card grids.
- Clearly separated tabs and answer history.
- Visible personal rank and relevant scores.

### Leaderboard
- A distinctive top-three typographic podium.
- A clean numbered list for remaining ranks.
- Separate Weekly Karma, Most Gay, and Top Questions categories.
- Always show the current user's own ranking when available.
- Use meaningful score and rank-change animations, not permanent glow or pulse effects.

### Authentication and consent
- Minimal layouts with clear typographic hierarchy.
- One prominent primary action.
- No generic gradient hero sections.
- Match the same visual system as the authenticated application.

## Motion system

Use purposeful, restrained animations:

- Button and interaction transitions: approximately 120–180ms.
- Tab and small content transitions: approximately 180–240ms.
- Modals and drawers: approximately 200–280ms, using opacity and modest movement.
- Question transitions: quick crossfade or restrained directional movement.
- Score changes: brief numerical transition or a small one-time highlight.

Prefer opacity and small transform changes. Avoid excessive spring bounce, parallax, cursor-following decoration, continuous ambient motion, and animations that block interaction.

Respect prefers-reduced-motion, keyboard interaction, and accessible focus states.

## Implementation instructions

1. Inspect the existing application and assets before modifying anything.
2. Identify the existing routes, components, design tokens, and functional interactions.
3. Establish the design system before redesigning individual pages.
4. Build reusable components and shared CSS variables.
5. Redesign the actual application, including authentication, consent, feed, card mode, profiles, settings, and leaderboard.
6. Preserve all existing backend integrations, API contracts, authentication flows, voting rules, scoring logic, and database behavior.
7. Do not replace functional features with mock data or decorative controls.
8. Test desktop and mobile layouts, loading states, errors, and keyboard accessibility.
9. Run the application and inspect the rendered output. Correct layout and typography problems instead of assuming the first implementation is finished.

The supplied specification is the visual source of truth. Do not invent a different aesthetic or add components merely because they are common in AI-generated websites.