# Design System Strategy: The Neon Monolith

## 1. Overview & Creative North Star
**Creative North Star: The Digital Aperture**

This design system is not a container; it is a lens. It rejects the "template-first" mentality of modern web design in favor of an atmospheric, editorial experience that feels like a high-end digital gallery. The aesthetic moves away from rigid, boxy layouts and instead uses light, depth, and scale to guide the eye. 

The goal is to create a sense of "Kinetic Futurism"—where the interface feels alive, powered by the vibrant neon energy of the accent colors against a void-like deep background. We achieve this through "Scale Shock" (the juxtaposition of massive typography against tiny, precise metadata) and "Luminous Layering" (using color and blur rather than lines to define space).

## 2. Colors
Our palette is rooted in a deep-space black, punctuated by high-frequency electric neons. These accents should be treated as light sources, not just fills.

*   **Primary (Cyan - #c1fffe):** The "Core Glow." Use this for primary actions and critical focus points.
*   **Secondary (Magenta - #ff51fa):** The "Energy Pulse." Use for secondary accents or to create depth in gradients.
*   **Tertiary (Lime - #b0ff96):** The "System Signal." Use for success states or specialized navigational cues.

### The "No-Line" Rule
Standard 1px borders are strictly prohibited for sectioning. They feel "webby" and generic. Instead, define boundaries through:
1.  **Background Shifts:** Transition from `surface` (#0e0e0e) to `surface-container-low` (#131313) to denote a new content block.
2.  **Negative Space:** Use the Spacing Scale (specifically `16` and `20` units) to let the "void" act as the separator.

### Surface Hierarchy & Nesting
Treat the UI as a physical stack of glass.
*   **Base:** `surface` (#0e0e0e).
*   **Sub-sections:** `surface-container-low` (#131313).
*   **Interactive Cards:** `surface-container` (#1a1a1a).
*   **Floating Elements:** `surface-container-highest` (#262626).

### The "Glass & Gradient" Rule
To achieve a "generative" feel, use gradients to add soul to flat surfaces. For hero backgrounds or CTA buttons, utilize a linear gradient from `primary` to `primary_container`. For floating overlays, apply a `backdrop-blur` (12px–20px) to semi-transparent surface tokens to create a frosted-glass effect.

## 3. Typography
The typographic system relies on extreme contrast to create an editorial feel.

*   **Display & Headlines (Space Grotesk):** These are structural elements. `display-lg` (3.5rem) should be used aggressively—don't be afraid to let headings bleed off-center or overlap subtle background elements.
*   **Body (Manrope):** Functional and clean. `body-md` (0.875rem) is our workhorse. It provides a technical, legible counterpoint to the expressive headlines.
*   **Label (Space Grotesk):** Use `label-md` for metadata and micro-copy. These should often be in all-caps with increased letter-spacing to feel like "serial numbers" on a futuristic device.

## 4. Elevation & Depth
In this system, depth is achieved through light and layering, never through heavy, muddy drop shadows.

*   **The Layering Principle:** Stacking tiers (e.g., a `surface-container-high` card placed on a `surface` background) creates a "soft lift." This is our primary method of hierarchy.
*   **Ambient Shadows:** If an element must float (like a modal), use an ultra-diffused shadow: `box-shadow: 0 20px 50px rgba(0, 255, 255, 0.05)`. Notice the shadow is tinted with the `primary` color, not black.
*   **The "Ghost Border" Fallback:** For accessibility in forms, if a border is required, use `outline-variant` at 20% opacity. It should be felt, not seen.
*   **Glassmorphism:** Use `surface_variant` at 60% opacity with a heavy backdrop-blur for navigation bars. This allows the neon accents of the content below to "bleed" through as the user scrolls.

## 5. Components

### Buttons
*   **Primary:** A solid fill of `primary-container`. No border. Text in `on-primary-fixed`.
*   **Secondary:** A "Ghost Button" using a 1px border of `primary` at 30% opacity. On hover, increase to 100% opacity with a subtle outer glow (0 0 15px `primary`).
*   **Tertiary:** Text-only in `secondary`, using `label-md` for a technical feel.

### Chips
*   **Selection:** Rounded `full`. Use `surface-container-highest` for the background and `primary` for the text. No borders.

### Cards & Lists
*   **Lists:** Strictly forbid divider lines. Use `1.5` (0.5rem) of vertical spacing between `surface-container` blocks to create separation.
*   **Cards:** Use `lg` (0.5rem) roundedness. Avoid "boxy" layouts by using asymmetrical padding—for example, `p-8` on the top/left and `p-4` on the bottom/right to create a sense of movement.

### Input Fields
*   **Minimalist Glow:** A transparent background with a `surface-container-highest` bottom border. On focus, the border transitions to `primary` and gains a 2px outer glow. Labels should use `label-sm` in `on-surface-variant`.

### Portfolio-Specific Components
*   **The "Work Blade":** A full-width image container that uses a diagonal clip-path or subtle parallax movement to break the horizontal grid.
*   **The "Glow-Cursor":** A custom cursor trailing a soft `secondary` magenta glow that reacts when hovering over interactive elements.

## 6. Do's and Don'ts

### Do:
*   **Embrace the Asymmetry:** Position your `display-lg` headings off-center or overlapping images to create a "designed" feel.
*   **Use High Contrast:** Pair `display-lg` directly with `body-sm` to create a sophisticated, high-end hierarchy.
*   **Respect the Dark:** Keep the background `#0e0e0e`. Avoid using grey; stay in the deep black/near-black realm to keep the neons vibrant.

### Don't:
*   **Use 100% Opaque Borders:** Never use a solid, high-contrast border. It kills the futuristic atmosphere.
*   **Center Everything:** Avoid the "bootstrap" look. Avoid centered text blocks; stick to left-aligned or intentionally staggered layouts.
*   **Overuse Gradients:** Use gradients for "moments" (CTAs, Heros), but keep the functional UI (inputs, menus) clean and flat to maintain high-end utility.