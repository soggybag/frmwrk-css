

# **Lesson 1**

## **Topic:** *Design Tokens + Custom Properties (CSS Variables)*

### **Goal:**

Students understand what design tokens are, why design systems use them, and how to extract tokens from real UI examples. Start your framework with a `tokens.css` file.


# **Learning Objectives**

By the end of this lesson, students will be able to:

1. Define **design tokens** and explain why they are used in modern CSS frameworks.
2. Create semantic custom properties for colors, spacing, and typography.
3. Separate **tokens** from **styles** (implementation).
4. Structure your project with a dedicated `tokens.css` file.
5. Replace all "magic numbers" in CSS with semantic `var(--…)` tokens.

### **Activity: “What makes a design system feel consistent?”**

Question: 

> “What makes buttons, cards, navbars, colors, fonts feel like they belong together?”

Common answers:

* Font scale
* Spacing scale
* Colors matching each other
* Reusable patterns

👉 All of that consistency comes from **design tokens**.

Set expectations:

“This class is not about writing CSS line-by-line. It’s about designing CSS frameworks the way professionals do — using architecture, tokens, layers, and components.”

# **What Are Design Tokens?**

### Tokens vs Implementation

* Tokens = **raw values** (e.g., colors, spacing, radius, typography)
* Implementation = **how components use tokens**

### Semantic naming

* Bad: `--blue`, `--light-blue2`
* Good: `--color-primary`, `--color-surface`, `--color-info-light`

### Tokens are NEVER used directly in HTML

They feed components like:

```css
.btn {
  background: var(--color-primary);
  padding: var(--space-md);
}
```

### Token types for their framework

Students will define tokens for:

* Colors
* Typography
* Layout / spacing
* Radii
* Shadows (optional)

### Theming via tokens

Small demo: swap tokens → complete theme change.

# **Token Extraction Lab**

Students work individually or in pairs.

### Task:

**Extract tokens from the example.**

Provide categories to fill:

```css
--color-background:
--color-foreground:
--color-primary:
--color-primary-hover:
--color-info:
--color-danger:

--space-xs:
--space-sm:
--space-md:
--space-lg:

--font-size-base:
--font-size-lg:
--font-stack:
--radius-md:
```

### Discuss:

* What counts as a token?
* What belongs in the stylesheet vs the token file?

Think semantically:

* “Instead of `--blue`, what’s the meaning of this color?”
* “Is this a one-off value or part of a scale?”

# **Writing a Token File (`tokens.css`)**

Show a real example:

```css
:root {
  /* Colors */
  --color-background: #ffffff;
  --color-foreground: #111111;
  --color-primary: #4f46e5;
  --color-primary-hover: #4338ca;
  --color-info: #0ea5e9;
  --color-danger: #ef4444;

  /* Spacing scale */
  --space-sm: 0.25rem;
  --space-md: 0.75rem;
  --space-lg: 1.5rem;

  /* Typography */
  --font-stack: system-ui, sans-serif;
  --font-size-base: 1rem;
  --font-size-lg: 1.25rem;

  /* Radii */
  --radius-md: 0.5rem;
}
```

Then show how components use tokens:

```css
.btn {
  background: var(--color-primary);
  padding: var(--space-md);
  border-radius: var(--radius-md);
}
```

Key takeaway:
👉 *Every component in their framework must use tokens.*

# **Lab: Convert Starter CSS to Token-Driven CSS**

Give students a small stylesheet with hard-coded values:

Example:

```css
button {
  background: #4f46e5;
  padding: 0.75rem 1rem;
  border-radius: 0.5rem;
  color: white;
  font-size: 1rem;
}
```

### Tasks:

1. Identify what should be tokens
2. Add tokens to `tokens.css`
3. Refactor the stylesheet to use `var(--…)`
4. Test with a second theme file
5. Swap themes live to verify everything is working

### Check your work:

* Naming clarity
* Missing tokens
* Over-tokenization 

---

# **Framework Setup**

Students create project structure:

```
/css
  tokens.css
  tokens-dark.css      (empty for now)
  frmwrk.css           (empty for now)
index.html              (demo page)
```

### Tasks:

* Create `tokens.css`
* Add at least:

  * Core colors
  * Text tokens
  * Spacing tokens
  * Radius tokens
* Link files into HTML

Encourage them to:

* Test by changing tokens
* Verify colors and spacing update globally
* Add a "theme toggle" button (JS optional)

### Questions:

1. “What makes a good design token name?”
2. “What is one token you created today and where do you plan to use it in your framework?”
3. “What’s the difference between a token and a utility class?”

### Preview next class:

> “Next class we introduce **Cascade Layers** and apply your tokens inside your framework’s architecture.
> By the end of next week, you’ll have a working component library.”

# **Homework (Optional but Recommended)**

### 🎯 **HW: Complete Your Token File**

Minimum:

* 6 colors
* 5 spacing values
* 2 typography tokens
* At least one alternate theme (dark, pastel, neon, etc.)




