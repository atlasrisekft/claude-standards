---
name: design-standards
description: Apply team design standards when building UI components, pages, or applications. Use when the user asks to build or modify any frontend interface, component, layout, or visual element.
tools: Read, Edit, Write, Bash, Glob, Grep
---

# Team Design Standards

Apply these rules to every piece of UI you build or modify.

## Stack

- **Components:** shadcn/ui — reach for a shadcn component first, extend with Tailwind
- **Styling:** Tailwind CSS utility classes for layout, spacing, and anything between components
- **Never** use inline styles or CSS modules unless explicitly asked

## Theme

- **Dark mode by default** on all new projects
- **Color tokens** (shadcn defaults — never hardcode hex values):
  - `background` / `foreground`
  - `card` / `card-foreground`
  - `muted` / `muted-foreground`
  - `accent` / `accent-foreground`
  - `destructive` / `destructive-foreground`
  - `border`, `input`, `ring`
- **Neutrals:** zinc/slate scale
- **Never** override shadcn's CSS variables without a clear reason

## Layout

- **Mobile-first** — design for small screens, scale up: `sm:` `md:` `lg:` `xl:`
- Use `flex` and `grid` via Tailwind; avoid fixed pixel widths
- Minimum tap target size: 44×44px on mobile

## Accessibility (WCAG 2.1 AA)

- Color contrast ratio: minimum 4.5:1 for text, 3:1 for large text
- All interactive elements must be keyboard-navigable
- Use semantic HTML (`button`, `nav`, `main`, `section`, not just `div`)
- Add `aria-label` on icon-only buttons and form inputs without visible labels
- Always include `focus-visible` ring styles — never `outline: none` without a replacement

## UX Laws (lawsofux.com) — apply by default

- **Fitts's Law** — make interactive targets large and close to where users are; primary CTA always prominent
- **Hick's Law** — fewer choices = faster decisions; max 5–7 items in a nav or dropdown before grouping
- **Jakob's Law** — follow familiar patterns; don't reinvent nav, modals, or form layouts
- **Miller's Law** — chunk content into groups of ~7 or fewer; use dividers, headings, and cards
- **Aesthetic-Usability Effect** — polished visuals increase perceived usability; spacing and alignment matter
- **Law of Proximity** — group related elements; use whitespace to separate unrelated ones
- **Law of Similarity** — identical styles for elements that behave the same; different styles for different behaviors
- **Cognitive Load** — hide complexity behind progressive disclosure; surface only what's needed per step
- **Doherty Threshold** — interactions must feel instant (<400ms); add skeleton loaders or spinners if longer
- **Peak-End Rule** — make the most important moment and the final step feel excellent
- **Von Restorff Effect** — one primary CTA per screen; don't let multiple elements compete for attention
- **Serial Position Effect** — put critical actions first or last in lists, navbars, and toolbars
- **Occam's Razor** — simplest solution that works; no decorative complexity
- **Goal-Gradient Effect** — show progress; users engage more as they approach completion
- **Zeigarnik Effect** — use progress indicators and save states; incomplete tasks feel unresolved

## Component Patterns

- Prefer composition over monolithic components
- Keep components under ~150 lines; split if larger
- Props should be typed (TypeScript preferred); avoid `any`
- Loading, empty, and error states are required for every data-fetching component
