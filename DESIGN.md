# Taiwo Oloni Portfolio — Open Design Redesign

## Intent

Present Taiwo as a practical automation specialist who can translate operational problems into maintainable systems. The interface should feel editorial, technical, calm, and credible while making case studies and the consultation action easy to find.

## Evidence boundary

Open Design Intelligence recommended Mastercard, IBM, and Vodafone as useful references. The implementation adapts general decisions only:

- Mastercard: warm off-white canvas, ink-led hierarchy, restrained flat surfaces, and low reliance on gradients.
- IBM: modular grid, hairline dividers, square controls, explicit states, and engineered information hierarchy.
- Vodafone: one decisive conversion accent and high-impact display scale.

The redesign does not use their logos, protected assets, proprietary typefaces, or brand-specific motifs. The coral and lime palette, workflow-grid illustration, content hierarchy, and component details are creative decisions for this portfolio.

## Color tokens

| Role | Value | Usage and state | Evidence boundary |
| --- | --- | --- | --- |
| Canvas | `#f3f0e8` | Default page and header background | Warm canvas is evidence-backed; exact value is a portfolio-specific decision |
| Paper | `#fffdf7` | Forms, tool chips, and light nodes | Portfolio-specific supporting surface |
| Ink | `#171a17` | Headings, primary CTA, dark project surface, footer | Ink-led hierarchy is evidence-backed; exact value is portfolio-specific |
| Muted text | `#5d635d` | Supporting text on canvas only | Portfolio-specific; 5.41:1 against canvas |
| Hairline | `#c8c8bd` | Structural dividers; never the only signal for state | Hairline structure is evidence-backed |
| Primary accent | `#ff6038` | Emphasis, focus, active hover, mechanical offset | Single decisive accent is evidence-backed; coral value is portfolio-specific |
| Signal | `#d8ff4f` | Workflow status, selected filter, dark-surface status label | Portfolio-specific secondary signal; always paired with text or icon |

Ink/canvas contrast is 15.41:1, ink/coral is 5.84:1, and ink/signal is 15.32:1. Disabled controls use reduced emphasis plus the native `disabled` attribute and never rely on opacity alone for meaning.

## Typography and spacing

- Primary family: `IBM Plex Sans`, with `Arial` and `sans-serif` fallbacks.
- Technical labels: `IBM Plex Mono`, with `Consolas` and `monospace` fallbacks.
- Hero: `clamp(3.35rem, 7.8vw, 7.25rem)`, weight 300, line-height .98.
- Section heading: `clamp(2.35rem, 5vw, 4.65rem)`, weight 300, line-height .98.
- Card heading: 1.28–1.55rem, weight 600, line-height .98–1.1.
- Body: 1rem base with line-height 1.58; lead text 1.08–1.28rem.
- Mono labels: .58–.78rem, weight 500–600, uppercase, with .035–.1em tracking.
- Geometry: square by default, 4px maximum general radius, no decorative card shadows.
- Spacing: 4/8px base rhythm with 76–112px section spacing.

## Layout and hierarchy

- Desktop uses a wide 1280px shell and a two-column hero with the value proposition first and workflow system second.
- Section headings pair a compact mono label with a large light-weight heading.
- Outcomes, services, projects, process steps, facts, and benefits use connected grid cells rather than floating cards.
- The primary CTA is solid ink; the consultation alternative is outlined. Hover uses coral plus a 3px mechanical offset.
- Case studies retain explicit placeholder/status language and surface workflow steps as bordered sequence cells.

## Responsive behavior

- The shell is capped at 1280px with 32px desktop side gutters.
- At 980px and below, navigation collapses to an explicit menu button; hero, about, trust, and contact grids become one column; four- and three-column sections become two columns.
- At 680px and below, the shell uses 14px side gutters, all content grids and forms become one column, actions become full-width, and decorative workflow connector lines are removed.
- The mobile hero headline uses `clamp(3rem, 15vw, 4.4rem)` and the workflow visual remains at least 440px tall.
- The case-study workflow changes from four columns to two at 980px and one at 680px.
- No breakpoint may introduce horizontal document overflow; verification targets are 390px, 768px, 1440px, and large desktop.

## Interaction and accessibility

- Default buttons are solid ink with canvas text; outlined secondary buttons keep a 1px ink border.
- Hover changes the primary button to coral, shifts it by 3px, and adds a 3px ink offset shadow. Pressed state returns the translation toward zero; keyboard focus remains independently visible.
- Disabled/loading submit controls retain their label or loading text, use the native `disabled` state, and must not respond to pointer activation.
- Empty video state includes an icon, heading, and explanatory text. Form errors render inline text associated with the field. Missing case studies render a dedicated 404 message and recovery link.
- All primary interactive controls retain at least a 42–48px target height.
- `:focus-visible` uses a 3px coral outline with 4px offset on every interactive element.
- Filters expose `aria-pressed`; FAQs expose `aria-expanded`; the mobile menu exposes `aria-controls` and `aria-expanded`.
- Every action is keyboard reachable in DOM order. The skip link appears on focus, the mobile menu can be toggled by keyboard, and accordion buttons retain native button semantics.
- Color is supported by labels, borders, icons, text, or position; status is never communicated by color alone.
- `prefers-reduced-motion: reduce` disables smooth scrolling, transitions, and animations.
- Contrast targets are WCAG 2.1 AA: normal text at least 4.5:1 and large text/UI indicators at least 3:1. Current core foreground/background pairs meet 5.41:1 or higher.
- Netlify form semantics, visible labels, inline errors, honeypot, real POST behavior, consent, and thank-you route remain unchanged.

## Content and implementation constraints

- Preserve all routes, editable data, project honesty labels, SEO, CSP, Netlify Forms, redirects, and test coverage.
- Do not introduce fake metrics, client names, testimonials, or proof.
- Keep the original blue-and-teal production design untouched for comparison.
