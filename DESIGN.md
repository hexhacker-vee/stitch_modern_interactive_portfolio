# Design System Document: The Neon Nocturne

## 1. Overview & Creative North Star
**Creative North Star: "The Digital Curator"**

This design system is built to move beyond the static, templated nature of standard portfolios. It treats the digital screen as a high-end gallery space where content isn't just displayed—it is curated. By leveraging a "Dark Mode" foundation with high-energy accents, we create a cinematic atmosphere. 

The system breaks traditional "boxed" layouts through **intentional asymmetry** and **tonal layering**. We avoid rigid grids in favor of overlapping elements and vast expanses of whitespace (breathing room), ensuring that the professional's work feels like a premium, bespoke exhibit rather than a generic list of projects.

---

## 2. Colors & Surface Philosophy
The palette is rooted in deep obsidian tones, punctuated by "electric" accents that guide the user's eye through the narrative.

### The Color Tokens
- **Background:** `#0c0e17` (The void)
- **Primary (Electric Purple):** `#b89fff` / `#ac8eff`
- **Secondary (Neon Blue):** `#00e3fd` / `#00d4ec`
- **Tertiary (Vibrant Magenta):** `#ff51fa`
- **Surface Tiers:** `surface-container-low` (`#11131d`) to `surface-container-highest` (`#222532`)

### The "No-Line" Rule
**Explicit Instruction:** Do not use 1px solid borders to define sections. Traditional borders create "trapped" layouts that feel dated. Boundaries must be defined strictly through:
1. **Background Color Shifts:** Placing a `surface-container-low` section against the `background` (`#0c0e17`).
2. **Tonal Transitions:** Using subtle gradients between surface tiers.

### The "Glass & Gradient" Rule
To achieve a premium feel, floating elements (modals, navigation bars, hover cards) must utilize **Glassmorphism**. 
- **Implementation:** Use a semi-transparent `surface-variant` with a `backdrop-filter: blur(20px)`.
- **Signature Textures:** Apply a linear gradient (Primary to Primary-Container) for main CTAs to add "soul" and depth that flat hex codes cannot provide.

---

## 3. Typography
We utilize a high-contrast typographic scale to create a clear editorial hierarchy.

- **Display & Headlines (Space Grotesk):** A bold, futuristic sans-serif. Use `display-lg` (3.5rem) for hero statements to command attention. The wide character tracking in Space Grotesk provides an "Architectural" feel.
- **Body & Labels (Inter):** A clean, highly legible sans-serif. `body-lg` (1rem) is the standard for storytelling. 
- **The Monospace Aesthetic:** For technical details or "meta" information (e.g., project dates, categories), use `label-md` with Inter, but increase letter spacing by 0.05em to mimic a sophisticated monospace vibe without sacrificing readability.

---

## 4. Elevation & Depth
In this system, depth is a product of light and layering, not shadows alone.

- **The Layering Principle:** Stack surfaces to create "Natural Lift." 
    - *Example:* A `surface-container-highest` card sitting on a `surface-container-low` section. 
- **Ambient Shadows:** Shadows are rarely used. When necessary (e.g., a floating project preview), use an extra-diffused shadow: `box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4)`. Never use pure black for shadows on colored surfaces; use a tinted version of the surface color to maintain "airiness."
- **The "Ghost Border" Fallback:** If a container requires definition against a similar background, use a "Ghost Border": `outline-variant` (`#464752`) at **15% opacity**.

---

## 5. Components

### Buttons
- **Primary:** Gradient fill (Primary to Primary-Dim), `md` (0.375rem) roundedness. No border. High-contrast `on-primary` text.
- **Secondary (The Glass Button):** Transparent background with a `backdrop-filter: blur(10px)` and a Ghost Border. 
- **Interaction:** On hover, buttons should "glow" using a subtle `box-shadow` of the button's own accent color at 30% opacity.

### Cards & Project Previews
- **Structure:** Forbid the use of divider lines. 
- **Separation:** Use vertical whitespace (e.g., 80px - 120px between projects) and `surface-container` shifts.
- **Interactive State:** Cards should subtly scale (1.02x) and shift background color from `surface-container-low` to `surface-container-high` on hover.

### Input Fields
- **Style:** Underline-only or Ghost-Bordered containers.
- **Focus State:** Transition the border/underline to `secondary` (Neon Blue) with a soft outer glow. Use `label-sm` for floating labels.

### Navigation (The Floating Dock)
- **Style:** A centered, glassmorphic pill using `surface-container-highest` at 70% opacity. 
- **Blur:** `backdrop-filter: blur(12px)`.
- **Rounding:** `full` (9999px).

---

## 6. Do's and Don'ts

### Do:
- **Use "Active" Whitespace:** Allow elements to breathe. A single project image might take up only 60% of the width, offset to the right, with text overlapping its edge.
- **Embrace Asymmetry:** Place headings off-center to create a dynamic, editorial flow.
- **Subtle Motion:** Use `cubic-bezier(0.23, 1, 0.32, 1)` for all transitions (the "Power Out" curve) to make the UI feel responsive and high-end.

### Don't:
- **Don't use 100% Opaque Borders:** This kills the "Glassmorphism" effect and makes the UI look "heavy."
- **Don't use Default Shadows:** Avoid the "dirty" look of standard grey shadows.
- **Don't Overcrowd:** If a screen feels "busy," remove an element. The premium feel comes from what you leave out.
- **Don't use Dividers:** If you feel the need for a `<hr>`, use a 40px gap of whitespace instead.