# Design System Strategy: The Neon Monolith

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Cyber-Editorial Monolith."** 

This is not a standard web interface; it is a high-fashion digital publication for a futuristic era. It blends the raw, structural honesty of Brutalism with the ethereal vibrancy of a neon-soaked cityscape. We break the traditional "template" look by utilizing heavy asymmetrical grids, intentional layering of type over imagery, and massive contrast between "The Macro" (giant headlines) and "The Micro" (dense technical metadata). The goal is to feel both architecturally solid and digitally fluid.

## 2. Colors
Our palette is rooted in an ultra-deep foundation, punctuated by high-energy accents that simulate light-emitting surfaces.

*   **Foundation:** The core is `surface` (#0e0e0e) and `surface_container_lowest` (#000000). This provides the "void" upon which our neon elements sit.
*   **The Neon Pulse:** Use `primary` (#ff89ab) and `tertiary_container` (#ff067f) for critical actions and brand moments. These colors should feel like they are glowing against the dark background.
*   **The "No-Line" Rule:** Do not use 1px solid borders to separate major sections. Division must be achieved through background shifts—placing a `surface_container_low` (#131313) block against a `surface` (#0e0e0e) base. 
*   **Surface Hierarchy & Nesting:** Treat the UI as stacked layers. A card should use `surface_container` (#1a1919) to lift slightly from the background. For deeper "inset" looks (like input fields), use `surface_container_lowest`.
*   **The "Glass & Gradient" Rule:** To achieve a premium feel, use backdrop-blurs on floating navigation or modals using `surface` at 70% opacity. Apply subtle linear gradients from `primary` to `primary_dim` on large CTAs to give them "soul" and depth beyond flat color.

## 3. Typography
Typography is our primary architectural tool. It must feel intentional, loud, and meticulously typeset.

*   **Display & Headline (Epilogue):** These are the "Monoliths." Use `display-lg` with **tight tracking (-4% to -6%)** and high weight. They should dominate the viewport, often being cropped or overlapped by other elements.
*   **Script Accents:** Pair massive headlines with an elegant, handwritten script (not in tokens, but as a brand layer). These should overlap the sans-serif type to break the grid and add a "human touch" to the cybernetic aesthetic.
*   **Body (Manrope):** Clean, geometric, and highly legible. Used for descriptions and long-form content.
*   **Labels (Space Grotesk):** These are the "Technical Metadata." Use `label-sm` or `label-md`, always **UPPERCASE**, with increased letter spacing (+10%). These should look like data readouts on a HUD (Heads-Up Display).

## 4. Elevation & Depth
In this design system, depth is conveyed through light and tonal layering rather than traditional drop shadows.

*   **The Layering Principle:** Depth is achieved by stacking `surface-container` tiers. A `surface_container_high` (#201f1f) element on top of `surface_dim` creates a natural, sophisticated lift.
*   **Ambient Shadows:** If a floating effect is required (e.g., a modal), use a massive blur (40px-80px) at a very low 5% opacity, using a tinted shadow color derived from `secondary_container`.
*   **The "Ghost Border" Fallback:** For buttons or card boundaries where definition is needed, use the "Ghost Border"—the `outline_variant` token at 15% opacity. Never use a 100% opaque border.
*   **Glassmorphism:** Use `surface_bright` with a 12px backdrop-blur for elements that hover over imagery. This ensures the neon glows from the images "bleed" into the UI.

## 5. Components

### Buttons
*   **Primary:** Filled with `primary_fixed`, text in `on_primary_fixed`. Use `rounded-md` (0.75rem).
*   **Secondary (Ghost):** A "Ghost Border" using `outline` at 20% opacity. On hover, fill with a subtle `surface_container_highest`.
*   **Tertiary:** Pure text using `label-md`, uppercase, with a small icon suffix.

### Technical Metadata (New Component)
*   Used for dates, version numbers, or "system status." Styled with `label-sm` (Space Grotesk), monospaced, colored in `on_surface_variant`. Often placed in corners or vertically along edges.

### Cards
*   Forbid divider lines. Separate content using `spacing-6` (2rem) of vertical white space or by nesting a `surface_container_highest` block inside a `surface_container` card.

### Input Fields
*   **Style:** Minimalist. No background fill, only a bottom "Ghost Border." 
*   **Focus State:** The border transitions to a `primary` glow, and the `label-sm` moves to an "active" state in `tertiary`.

### Chips
*   **Action Chips:** High-contrast capsules. `surface_container_highest` background with `on_surface` text. Use `rounded-full`.

## 6. Do's and Don'ts

### Do
*   **DO** overlap elements. Let a massive headline sit behind a high-resolution image.
*   **DO** use the technical metadata labels to fill "dead space" in the corners of containers.
*   **DO** use high-vibrancy `secondary` (#c47fff) for soft glows/blurs behind primary content.
*   **DO** strictly follow the `0.75rem` (12px) corner radius for a "soft-tech" feel.

### Don't
*   **DON'T** use standard 1px borders to box in content; it ruins the "editorial" flow.
*   **DON'T** use pure white (#ffffff) for body text; use `on_surface_variant` (#adaaaa) to maintain the cinematic, low-light atmosphere.
*   **DON'T** center-align everything. The system thrives on "weighted asymmetry"—heavy elements balanced by small clusters of dense data.
*   **DON'T** use standard drop shadows. If it doesn't look like a "glow," it doesn't belong.