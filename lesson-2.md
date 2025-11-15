# **Lesson 2 **

## **Topic:** *Cascade Layers for CSS Framework Architecture*

### **Context:**

You have already created a **`tokens.css`** file in Lesson 1.
Today, they learn how to organize their framework into predictable, scalable `@layer`s.

# **Learning Objectives**

By the end of this lesson, students will:

1. Understand **why** design systems use multiple layers.
2. Know the difference between **base**, **components**, **utilities**, and **overrides** layers.
3. Use `@layer` to avoid specificity wars.
4. Organize your CSS framework into a maintainable architecture.
5. Deploy a real-world pattern used in Bootstrap 5.3+, USWDS, and Material Web.

# **“Where Should This Rule Go?”**

Display on board/screen:

```
h1 { font-size: 2rem; }
.frmwrk-card { padding: 1rem; background: white; }
.mt-1 { margin-top: 0.25rem; }
button.btn-primary { background: var(--color-primary); }
body { font-family: var(--font-stack); }
```

Ask students to classify each rule as:

* **Base**
* **Component**
* **Utility**

# **Cascade Layers (Concept + Syntax)**

```
/* Framework Structure */
@layer tokens, base, components, utilities;

/* Example */

@layer base {
  body { font-family: var(--font-stack); }
  h1 { font-size: 2rem; }
}

@layer components {
  .btn { padding: var(--space-md); }
  .card { background: var(--color-surface); }
}

@layer utilities {
  .mt-1 { margin-top: var(--space-sm); }
}
```

### 1. `@layer` controls **order**, not specificity

Explain:

* Normally, CSS follows “later wins.”
* **Layers override that rule**.
* The order listed at the top wins.

### 2. Layers are a design-system superpower

* They prevent specificity battles.
* They allow utilities to win over components *predictably*.
* They allow authors to add a *user override* layer on top of the framework.

### 3. Recommended layer order (industry-standard)

```
@layer tokens, base, components, utilities, overrides;
```

Why:

* **tokens** = raw values
* **base** = element styles (h1, p, a, body)
* **components** = card, btn, navbar
* **utilities** = `.mt-1`, `.text-center`, `.grid-2`
* **overrides** = last-chance custom CSS

### 4. Layers allow *easy theming*

Theme overrides only need to change values in the `tokens` layer or outside of layers.

### 5. Layers intentionally

Framework code becomes:

* predictable
* cleaner
* more robust
* more “Bootstrap-like” in structure

# **Active Learning Lab 1: Sorting the Styles**

Give students a page from your framework demo and a pile of sticky notes (or use an online shared doc).

### **Task: Sort these example rules into the correct layer.**

Provide a printout or slide with 15–20 rules. Example:

```
.frmwrk-card { background: var(--color-surface); }
h3 { line-height: 2rem; }
.navbar { display: flex; align-items: center; }
.text-center { text-align: center; }
input[type=text] { border: 2px solid var(--color-border); }
:root { --color-primary: oklch(...); }
.btn { padding: var(--space-sm) var(--space-md); }
```

### Students work individually → then pair up

### Instructor leads discussion:

* Where did disagreements happen?
* Why?
* What rules are ambiguous? (Great teaching moment.)

# **BREAK**

# **Active Learning Lab 2: Convert Their Framework to Layers**

Students open their framework repos.

### Step 1 — Add the top declaration

```css
@layer tokens, base, components, utilities;
```

### Step 2 — Wrap their existing CSS

Example:

```css
@layer base {
  body {
    font-family: var(--font-stack);
    font-size: var(--font-size);
  }
  h1 {
    margin: 0;
  }
}
```

```css
@layer components {
  .navbar { ... }
  .frmwrk-card { ... }
  .info { ... }
}
```

```css
@layer utilities {
  /* Will add next week */
}
```

### Step 3 — Testing With Conflicts

Instructor gives them a “conflict demo”:

```css
.card { background: pink !important; }
```

Ask:

“What happens if this rule is added in a new `@layer author` after your framework?”

They see how predictable overrides become.

### Step 4 — Theme swap test

They import:

```html
<link rel="stylesheet" href="tokens.css">
<link rel="stylesheet" href="tokens-dark.css">
<link rel="stylesheet" href="frmwrk.css">
```

Verify:

* base styles → unchanged
* components → follow new tokens
* layer ordering → still works

# **Framework Architecture Setup**

* Finish wrapping all rules into correct layers
* Move missing values into tokens
* Clean naming inconsistencies
* Remove leftover “magic numbers”
* Test with *two* themes

Check:

* Does you `tokens` layer contain only variable definitions?
* Are *all* typography rules in `@layer base`?
* Are cards, navbars, toggles in `@layer components`?
* Did you accidentally create a utility rule that belongs in components?

# **Review + Exit Ticket + Homework**

### Questions:

1. “Which rule did you move from components → base and why?”
2. “What surprised you about using `@layer`?”
3. “How would you explain `@layer` to a junior developer?”

### Homework:

* Create **one new component** (e.g., alert, badge, grid block) and place it in `@layer components`.
* Add at least **one utility class** (e.g., `.mt-2`, `.text-lg`).
* Make sure both use your tokens.

# Deliverables After This Lesson

By the end of Lesson 2, every student should have:

✓ A complete `tokens.css`
✓ A framework file (`frmwrk.css`) with 3 layers:

* `@layer base`
* `@layer components`
* `@layer utilities`
  ✓ All base styles migrated
  ✓ All components grouped
  ✓ Tokens fully integrated
  ✓ A working theme swap
