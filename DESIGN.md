# Design System Document

## 1. Overview & Creative North Star: "The Editorial Sanctuary"

This design system is built to transform a digital interface into a tactile, high-end boutique experience. The Creative North Star, **"The Editorial Sanctuary,"** moves away from the clinical, grid-locked nature of standard fitness apps. Instead, it draws inspiration from high-fashion editorial spreads and architectural minimalism.

The system emphasizes **intentional asymmetry** and **tonal depth**. Rather than centering every element, we use the "breathing room" of our cream-toned backgrounds to push content into unexpected, elegant compositions. Overlapping elements—such as a serif headline partially masking an image or a button floating across a container boundary—create a sense of layered physical space, mirroring the precision and flow of a Pilates practice.

---

## 2. Colors

The palette is rooted in a warm, sophisticated "Cream and Burgundy" foundation. It is designed to feel human, serene, and premium.

### Palette Strategy
- **Primary (`#770100`) & Primary-Container (`#a20100`):** These deep reds represent the "heart" and strength of the brand. Use them sparingly for key actions and focal points.
- **Surface & Background (`#fbf9f2`):** A warm, off-white base that avoids the harshness of pure white, providing a serene environment for content.
- **Tertiary (`#001eac`):** A sophisticated deep blue used only for subtle high-contrast accents or specific utility states to maintain professional polish.

### The "No-Line" Rule
**Explicit Instruction:** 1px solid borders are strictly prohibited for sectioning or containment. Boundaries must be defined solely through background color shifts. For example, a "Schedule" section should be distinguished from a "Bio" section by transitioning from `surface` to `surface-container-low`.

### Surface Hierarchy & Nesting
Treat the UI as a series of stacked fine papers. Use the tiers to define importance:
- **Base Level:** `surface` (Main background)
- **Secondary Content:** `surface-container-low` (Subtle grouping)
- **Interactive Cards:** `surface-container-lowest` (The "whitest" tier, suggesting it is closest to the user)

### The "Glass & Gradient" Rule
To add "soul" to the interface, avoid flat-only design.
- **Glassmorphism:** Use `surface` at 80% opacity with a `20px` backdrop-blur for floating navigation bars or overlay modals.
- **Signature Textures:** Use a subtle radial gradient on Hero CTAs transitioning from `primary` (`#770100`) to `primary-container` (`#a20100`) to create a soft, velvet-like visual depth.

---

## 3. Typography

The typography scale balances the authority of a classic serif with the modern clarity of a geometric sans-serif.

- **Display & Headline (Noto Serif):** These are the "voice" of the brand. Use large scales and tight letter-spacing for a high-end editorial feel. Headlines should feel like titles in a premium magazine.
- **Title & Body (Manrope):** Chosen for its clean, open proportions. It ensures legibility during the functional parts of the user journey (booking, reading class descriptions).
- **Labels (Manrope):** Small-caps or increased letter-spacing (`0.05em`) should be applied to `label-md` to denote luxury in the smallest details.

| Role | Font Family | Size | Intent |
| :--- | :--- | :--- | :--- |
| **Display-Lg** | Noto Serif | 3.5rem | Hero moments, high-impact branding. |
| **Headline-Md** | Noto Serif | 1.75rem | Section headers, editorial storytelling. |
| **Title-Md** | Manrope | 1.125rem | Sub-headers and card titles. |
| **Body-Lg** | Manrope | 1rem | Primary reading experience. |
| **Label-Sm** | Manrope | 0.6875rem | Metadata, eyebrow text, button labels. |

---

## 4. Elevation & Depth

We convey hierarchy through **Tonal Layering** and ambient light, never through heavy shadows or structural lines.

- **The Layering Principle:** To create a "lifted" card, place a `surface-container-lowest` element onto a `surface-container` background. The slight shift in brightness creates a more sophisticated "lift" than a drop shadow.
- **Ambient Shadows:** Shadows are reserved only for floating elements (like a "Book Now" FAB). They must be ultra-diffused: `blur: 40px`, `y-offset: 8px`, `opacity: 6%`, using a tinted shadow color derived from `on-surface` (`#1b1c18`).
- **The "Ghost Border" Fallback:** If a divider is essential for accessibility, use the `outline-variant` token at **15% opacity**. It should be felt, not seen.
- **Depth through Imagery:** Encourage the use of photography with soft focus backgrounds (bokeh) to reinforce the system's depth principles within the content itself.

---

## 5. Components

### Buttons
- **Primary:** Background `primary` (`#770100`), Text `on-primary` (`#ffffff`). Shape: `sm` (0.125rem) for a sharp, architectural look. No heavy rounding; we prefer the precision of slight corners.
- **Secondary:** Transparent background with a "Ghost Border" (15% opacity `outline-variant`).
- **Interaction:** On hover, the primary button should shift to `primary-container` with a subtle `4px` vertical lift.

### Cards & Lists
- **Layout:** Strictly forbid divider lines between list items. Use `spacing-6` (2rem) of vertical white space to separate items.
- **Surface:** Cards should use `surface-container-highest` to pop against a `surface` background.

### Input Fields
- **Style:** Underline-only style or a very soft `surface-variant` background.
- **Focus State:** Transition the underline from `outline-variant` to `primary` with a 200ms ease-in-out.
- **Labels:** Use `label-md` positioned above the input, never placeholder-only.

### Specialized Component: The "Class Float" Chip
- Used for class types (e.g., "Reformer," "Mat").
- **Style:** `surface-container-lowest` with a `10%` `primary` border. Use `full` roundedness (9999px) to contrast against the sharp-edged buttons.

---

## 6. Do's and Don'ts

### Do
*   **Do** use asymmetrical margins. A text block might be indented further than the headline above it to create a sophisticated, "designed" feel.
*   **Do** allow images to "bleed" off the edge of the screen or container.
*   **Do** prioritize the `surface` palette over white. Pure white (`#ffffff`) should only be used for the most prominent interactive elements (`surface-container-lowest`).

### Don't
*   **Don't** use 100% black text. Always use `on-surface` (`#1b1c18`) to maintain the warm, premium tone.
*   **Don't** use standard "Material" or "Bootstrap" shadows. They are too heavy and break the serenity of the "Sanctuary" vibe.
*   **Don't** crowd the interface. If a screen feels busy, increase the spacing tokens (move from `spacing-6` to `spacing-10`). High-end design is defined by what you leave out.