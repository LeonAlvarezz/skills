---
name: paint-in
description: Paint in a low-level wireframe component by replacing it with a detailed, high-fidelity UI component based on a context file and original screenshot. Use when the user says /paint-in or asks to bring a wireframe section to life.
---

# Paint-In Skill

## Purpose
Take a project's low-level wireframe component (gray and white layout) and replace it with a polished, premium UI component in a separate file, using its corresponding context file (`page.context.md` or `{page}.context.md`) and design details as guidance.

## Workflow

### 1. Read Context and Wireframe
- Read the context file (`{page}.context.md`) to understand the layout and component structure. If you don't know which one to read please ask.
- Read the target wireframe file (e.g. `src/App.vue`, `src/components/Home.vue`, etc.) to locate the component layout and ID.

### 2. User Component Selection
- Ask the user which specific section or component from the context file/wireframe they want to paint in.
- Wait for the user's selection.

### 3. Design Verification and Requesting Design Files
- Verify if you have clear, high-resolution design guidance (e.g. a screenshot, layout details, or reference UI specs) showing exactly how the component should look.
- **CRITICAL RULE**: If you do not know or are unsure how the final design should look, **you MUST ask the user for a screenshot or design reference before doing anything else**. Do not infer the design from adjacent components, brand colors, context notes, or a different screenshot unless the user explicitly approves inference.
- **STOP CONDITION**: When the selected component does not have an exact visible reference, stop after requesting the screenshot/reference. Do not present a design breakdown, implementation plan, asset plan, or code proposal until the user provides the reference or explicitly says to infer.
- **REFERENCE MATCH RULE**: A screenshot/reference only counts as clear design guidance if it shows the selected component itself, not merely the surrounding page or a related component. If it only shows related styling, ask for the selected component's screenshot or ask whether inference is acceptable.
- **ASSET REQUEST RULE**: If you suspect that custom SVGs, PNG images, or icons are needed for the component, do not try to hand-craft complex SVGs on your own. Instead, gather a list of all missing assets, specify the name and folder (e.g., `src/assets/`) where you need them, and ask the user to provide and place them in the project.

### 4. Design Review and Back-and-Forth Alignment
- Only start this step after clear selected-component design guidance exists, or after the user explicitly approves inferred design.
- **Before implementing any code**, you must present a detailed breakdown to the user of:
  - What you see in the design reference (layout, typography, gradients, custom graphics, spacing, visual cues).
  - How you plan to structure the component (elements, state, behaviors, animations).
- When recreating UI from screenshots, do not map screenshot pixels directly to CSS sizes. First normalize measurements to the actual target viewport/component width, then choose font sizes, spacing, and controls that fit without overlap at the app viewport.
- Engage in a back-and-forth discussion with the user.
- **WAIT for approval**: Do not implement the component until the user explicitly confirms the breakdown/design is "good enough" to proceed.

### 5. Paint In via Component Extraction
- Create a **new separate file** for the painted-in component (e.g. under `src/components/` or a modular structure).
- Implement the polished, high-fidelity UI component in this new file using premium styling guidelines (rich typography, smooth gradients, transitions, interactive states).
- Import and mount the newly created component back into the target wireframe file, replacing the low-level wireframe element/shape.
- Ensure the parent layout structure and sibling wireframe elements remain intact.
- Ensure to use Tailwind if the project has it already set up. Do not generate a full CSS stylesheet for painted components in Tailwind projects; use CSS only as a minimal fallback for effects Tailwind cannot express cleanly, such as complex clip-path shapes.
- Update the context file's component mapping table or notes to reflect that this section is now `[painted]`.
