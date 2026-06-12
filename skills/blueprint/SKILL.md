---
name: blueprint
description: Create a structured page context and a simple gray-and-white low-level wireframe from a screenshot. Use when the user requests a blueprint, asks to analyze or break down a page screenshot, or wants a low-level wireframe.
---

# Blueprint Skill

## Purpose
Analyze a provided screenshot of a page and break it down into clean sections and components. Generate a context file documenting this layout, then create a simple low-level wireframe in a target file.

## Workflow

### 1. Analysis and Component Breakdown
- Inspect the provided screenshot and identify the high-level sections and layout structure (e.g., Hero page, Features, About Us, CTA section, Footer).
- Break the page down into individual components or regions.
- List all sections/components on the page in a clean, hierarchical format.

### 2. Create the Context File
- Write the breakdown list into a project-scoped context file.
- The context file name must a specific page name `{page}.context.md` (e.g., `home.context.md` or `dashboard.context.md`).
- Inside the context file, detail each section's contents, purpose, parent-child relations, and layout description.

### 3. Ask for the High Fidelity Wireframe Target File
- **CRITICAL RULE**: If the user did not specify which file the low-level wireframe should be written to, **you MUST ask the user** which file they want to write the wireframe in.
- Do not write the high fidelity wireframe code until you have a confirmed file path from the user.

### 4. Create the High Fidelity Wireframe
- Implement a simple high fidelity wireframe containing the shape of all components defined in the context file.
- **Visuals & Color**:
  - Keep it extremely simple: gray and white shapes only.
  - Do NOT assume any colors.
  - Use simple CSS/Tailwind bounds, borders, and backgrounds (e.g., `bg-gray-100`, `border-gray-300`, text placeholders).
- **Assets & Custom Elements**:
  - Do NOT try to assume any assets (images, custom icons, illustrations).
  - Do NOT try to DIY custom illustrations or assets. Use simple gray boxes as placeholders (e.g., a box with text "Asset Placeholder").
  - Make it very easy for the user to manually input values or actual assets later.
- Write this high fidelity wireframe structure into the specified file.
