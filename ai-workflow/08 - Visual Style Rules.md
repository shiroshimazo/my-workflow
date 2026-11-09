Applies to any task that creates or changes a user interface.
Goal: modern, minimal, intentional. It should not look AI-generated or templated.

## Priority
Usability and accessibility come first, then style. Never sacrifice contrast, clarity, or tap targets for looks.

## Before designing
1. Define design tokens first (colors, type scale, spacing scale, radius, border, shadow) in one place. Never invent values inline.
2. Choose a visual direction that fits the product and audience, and record it in `context.md`. Do not default to a generic SaaS look.
3. Reuse existing tokens and components. Do not restyle what already exists.

## Minimal means
- Remove before adding. Every element must earn its place.
- Generous whitespace. Use a consistent spacing scale (for example 4/8/12/16/24/32/48).
- One accent color, used sparingly for primary actions and key states.
- A restrained neutral palette (3-5 neutrals) with strong text contrast.
- Hierarchy through size, weight, and spacing, not decoration.
- Flat surfaces with thin 1px borders. Use shadows rarely and only soft ones.

## Typography
- One font family, two weights at most for most screens.
- A defined scale (for example 12/14/16/20/28/40). Body text 14-16px.
- Left-align text. Keep line length around 60-75 characters.
- Tight, short headings. No gradient text.

## Layout
- Align everything to a grid. Fewer, larger sections over many small boxes.
- Do not wrap everything in cards. Use spacing and dividers first.
- Vary layout to fit the content. Do not repeat identical card grids.
- Mobile-first, responsive, with comfortable tap targets (44px minimum).

## Components
- One icon set, one stroke weight, consistent size. Never emoji as icons.
- One radius value family (for example 6-8px). Do not round everything fully.
- Buttons: one clear primary per view, secondary and ghost styles for the rest.
- Tables and lists: clean rows, subtle dividers, no zebra stripes unless needed.
- Inputs: clear labels, visible focus state, restrained styling.

## Motion
- Subtle and fast (150-250ms), ease-out. Purpose only: feedback and state change.
- No bouncing, floating, parallax, or looping decoration.
- Respect `prefers-reduced-motion`.

## States
Every screen and component needs loading, empty, error, and success states. Design the empty state with a short helpful message and an action.

## Dark mode
If supported, use token-based themes. Do not just invert colors. Re-check contrast.

## AI-slop blacklist (never do these)
- Purple-to-blue or rainbow gradients, gradient text, neon glows
- Glassmorphism or heavy blur used by default
- Large soft shadows on every card
- Emoji used as icons or decoration
- Centered hero with big gradient headline and two buttons
- Rows of three identical feature cards with icon, title, and description
- Fake stats, fake testimonials, lorem ipsum, or placeholder logos
- Filler copy ("Welcome back!", "Unlock the power of...", "Seamless experience")
- Random decorative blobs, orbs, grids, or sparkles
- Different radius, spacing, or colors on every component
- Using a default component library look without adjusting tokens

## Copy
Short, direct, specific. Say what the thing does. No hype words.

## Self-check before finishing
- [ ] Uses only defined tokens
- [ ] Could I remove any element without losing meaning?
- [ ] One clear primary action per view
- [ ] Contrast and focus states pass
- [ ] No item from the AI-slop blacklist
- [ ] Looks intentional, not like a template