# Design System Document: The Scholarly Monograph

## 1. Overview & Creative North Star
**Creative North Star: "The Digital Curator"**

This design system rejects the cluttered, "resume-as-a-webpage" template. Instead, it draws inspiration from high-end architectural monographs and premium editorial journals. The goal is to position the graduate student not just as a candidate, but as a thought leader. 

We achieve this through **Intentional Asymmetry** and **Tonal Depth**. By utilizing expansive white space (the "breathing room" of a gallery) and a sophisticated hierarchy of slate and deep ink tones, we create an environment where research papers feel like curated exhibits rather than list items. The UI should never compete with the content; it should frame it.

---

## 2. Colors & Surface Philosophy
The palette is rooted in a "Deep Academic" spectrum, moving away from bright, distracting primaries toward a world of midnight blues (`primary: #002045`) and soft, paper-like neutrals (`background: #f9f9ff`).

### The "No-Line" Rule
Standard 1px borders are strictly prohibited for sectioning. They create visual noise and "trap" the content. Instead, define boundaries through:
- **Tonal Shifts:** Transitioning from `surface` to `surface-container-low`.
- **Vertical Rhythm:** Using large increments from the Spacing Scale (e.g., `16` or `20`) to separate thoughts.

### Surface Hierarchy & Nesting
Treat the UI as a series of layered vellum sheets. 
- **Base Level:** `surface` (#f9f9ff) for the main page body.
- **Mid Level:** `surface-container-low` (#f0f3ff) for secondary content sections like "Technical Skills."
- **Focus Level:** `surface-container-lowest` (#ffffff) for primary cards to create a subtle, "popping" effect against the slightly tinted background.

### The "Glass & Gradient" Rule
For navigation bars or floating action buttons, use **Glassmorphism**. Apply `surface_variant` with a 70% opacity and a `24px` backdrop-blur. To add "soul" to hero headers, use a subtle linear gradient from `primary` (#002045) to `primary_container` (#1a365d) at a 135-degree angle.

---

## 3. Typography
We utilize a pairing of **Manrope** (Display/Headline) for a modern, geometric authority and **Inter** (Body/Label) for unparalleled technical readability.

*   **Display & Headlines (Manrope):** Use `display-lg` (3.5rem) for name/branding and `headline-md` (1.75rem) for section headers. The tight tracking and bold weight of Manrope convey confidence.
*   **Body & Titles (Inter):** Use `body-lg` (1rem) for research abstracts. The generous x-height of Inter ensures that even dense academic jargon remains approachable.
*   **The Narrative Scale:** Always lead with a `title-lg` for project names, followed by `body-sm` for metadata (date, journal, role) in `on_surface_variant` (#43474e).

---

## 4. Elevation & Depth
In this system, elevation is an optical illusion created by light, not lines.

*   **The Layering Principle:** Rather than shadows, place a `surface_container_lowest` card on a `surface_container` background. The slight shift in brightness provides all the separation required for a clean, academic look.
*   **Ambient Shadows:** If a card requires a "lift" on hover, use an extra-diffused shadow: `0 20px 40px rgba(18, 28, 44, 0.06)`. Note the use of `on_surface` (#121c2c) as the shadow tint rather than pure black.
*   **The Ghost Border Fallback:** For accessibility in input fields, use `outline_variant` (#c4c6cf) at **20% opacity**. It should be felt, not seen.

---

## 5. Components

### Cards (Publications & Projects)
*   **Structure:** No borders. Use `surface_container_lowest` as the card base.
*   **Spacing:** Internal padding of `8` (2.75rem) to give the abstract room to breathe.
*   **Interaction:** On hover, transition the background to `surface_bright` and apply the Ambient Shadow.

### Skill Tags (Chips)
*   **Visuals:** Use `secondary_container` (#d5e0f7) for the background with `on_secondary_container` (#586377) for text.
*   **Shape:** Use `roundedness.full` (9999px) for a soft, modern pill shape.
*   **Typography:** `label-md` (Inter, 0.75rem) in all-caps with 0.05rem letter spacing for a "technical" feel.

### Navigation Layout
*   **The Sidebar/Header:** Use a "Sticky Glass" header. Height: `12` (4rem). 
*   **Links:** Use `title-sm` with a 2px underline offset. The underline should only appear on `primary` (#002045) when active, using a width of 1px.

### Buttons
*   **Primary:** Background `primary` (#002045), text `on_primary` (#ffffff). Shape: `roundedness.md`.
*   **Tertiary (Ghost):** No background. Text `primary`. Use for "Read More" links.

---

## 6. Do's and Don'ts

### Do
*   **DO** use `spacing.20` or `spacing.24` between major sections (e.g., between "Education" and "Publications").
*   **DO** use `tertiary_fixed` (#ffddba) sparingly as a highlight color for a "Gold Medal" or "Award" tag.
*   **DO** align text to a generous left-margin grid to create a sophisticated, asymmetrical editorial layout.

### Don't
*   **DON'T** use 100% black (#000000) for text. Always use `on_surface` (#121c2c) to maintain the sophisticated slate-blue tonal range.
*   **DON'T** use divider lines to separate list items. Use a `1.5` (0.5rem) vertical gap and a background color shift instead.
*   **DON'T** use standard "drop shadows" with high opacity. If it looks like it's floating high off the page, it's too heavy for this system.