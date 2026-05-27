# AI vs DevOps — Agent Guidelines

This document provides context for agents working on the **AI vs DevOps** blog by Eugene Burachevskiy.

- **Live URL:** https://eugene-burachevskiy.github.io/ai-vs-devops-blog/
- **Platform:** Static site hosted on GitHub Pages
- **Languages:** English (primary) and Russian (marked with `RU` tag)
- **Author:** Eugene Burachevskiy

---

## 1. Blog Overview & Purpose

The blog covers the intersection of **AI engineering** and **DevOps/infrastructure**. Target audience:

- DevOps engineers integrating AI into enterprise workflows
- AI engineers building production-grade systems
- Platform engineers designing agent infrastructure
- Tech leads making architectural decisions at the AI/infra boundary

Core thematic areas:
- AI agent infrastructure and sandboxing
- LLM engineering (caching, serving, optimization)
- Infrastructure as Code and platform engineering
- AI-assisted development workflows and tooling
- Spec-driven development and agent orchestration

---

## 2. Visual Styling

### Design System
The blog uses a custom dark theme. All CSS variables are standardized:

```css
--bg-primary: #0a0e1a;
--bg-secondary: #111827;
--bg-card: #1a1f2e;
--bg-code: #0d1117;
--text-primary: #f0f4f8;
--text-secondary: #94a3b8;
--text-muted: #64748b;
--accent-blue: #3b82f6;
--accent-cyan: #06b6d4;
--accent-purple: #8b5cf6;
--accent-green: #10b981;
--accent-orange: #f59e0b;
--accent-red: #ef4444;
--border-color: #1e293b;
```

**Fonts:**
- Body: `Inter` (weights 300-800)
- Code: `JetBrains Mono` (weights 400-600)

### Layout Conventions
- **Index page:** Hero section + featured article card + article list cards
- **Article pages:** Hero with title/badge + optional TOC sticky nav + numbered sections
- **Cards:** `border-radius: 16px`, hover effect with `box-shadow-glow` and `translateY(-2px)`
- **Section numbers:** 48x48px gradient badges with white text
- **Code blocks:** `background: var(--bg-code)`, `border-radius: 12px`
- **Blockquotes:** Left blue border, card background, large decorative quote mark
- **Highlight boxes:** Gradient border with blue tint for key takeaways
- **Tables:** Wrapped in `.table-wrapper` with rounded borders

### Article Meta Format
```html
<div class="article-meta">
    <span>📅 Month Day, Year</span>
    <span>⏱️ N min read</span>
    <span class="lang-tag">RU</span>  <!-- only for Russian articles -->
</div>
```

---

## 3. Tone of Voice

### Core Principles
1. **Technical depth over hype** — Every claim should be backed by data, configuration, or real-world examples.
2. **Practical first** — Readers should leave with actionable patterns, not just concepts.
3. **Direct and concise** — Avoid filler. Use short paragraphs. Bold the key insight.
4. **Conversational but authoritative** — Write like you're explaining to a smart colleague, not a textbook.

### Writing Patterns
- Use **numbered sections** for long-form deep dives ("1. Harness Engineering", "2. Caching Strategies")
- Use **comparison tables** for architectural decisions
- Use **decision trees** (`.decision-tree` class with monospace styling) for flow logic
- Use **highlight boxes** for "Key Insight" or "Production Guidance"
- Use **blockquote** for important quotes or paradigm shifts
- Start sections with the problem, then the solution, then the implementation

### Language
- **English articles:** Technical English, standard for engineering blogs
- **Russian articles:** Mark with `lang="ru"` in `<html>` and add `<span class="lang-tag">RU</span>` in meta. Use technical terms in English where there's no established Russian equivalent (e.g., "caching", "deployment", "sandbox").

---

## 4. Content Structure

### Article Types

| Type | Description | Example |
|------|-------------|---------|
| **Deep Dive** | Comprehensive technical guide with 10+ sections | "Advanced LLM/AI Engineering" |
| **Tutorial** | Step-by-step implementation guide | "Notifications from Claude Code to Telegram" |
| **Opinion/Analysis** | Architectural comparison or methodology discussion | "KISS vs DRY in IaC" |
| **Quick Take** | Short analysis of a news item or product release | (future format) |

### Standard Article Sections (for Deep Dives)
1. Hero with title, category badge, and meta
2. Table of Contents (sticky nav for long articles)
3. Problem statement / context
4. Technical explanation
5. Implementation / configuration details
6. Real-world metrics or examples
7. Tradeoff analysis (tables)
8. Production guidance / best practices
9. Summary / key takeaways
10. Related resources / links

---

## 5. Publishing Process

### Repository Structure
```
ai-vs-devops-blog/
├── index.html          # Landing page — MUST update when adding articles
├── articles/
│   ├── <slug>.html     # Individual article files
│   └── ...
├── images/
│   ├── hero_ai.jpg     # Default OG image
│   ├── favicon.jpg
│   └── <article-specific>.jpg
├── README.md
└── AGENTS.md           # This file
```

### Adding a New Article

1. **Create article HTML** in `/articles/<descriptive-slug>.html`
   - Use existing articles as templates for CSS and structure
   - **Include OpenGraph and Twitter Card meta tags** (required for link previews in Telegram, Twitter/X, LinkedIn, Discord, Slack, and other messengers)
   - **Include favicon** (`<link rel="icon" type="image/jpeg" href="../images/favicon.jpg">`) for the browser tab icon
   - Use descriptive `<title>` and `og:description`

2. **Add images** to `/images/` if needed
   - Use `.jpg` or `.png`
   - Optimize for web (hero images ~1200x630 for OG)

3. **Update `index.html`** to include the new article in the list
   - Add article card in `.articles-list`
   - Assign sequential article number
   - Include category badge, title, description, date, and language tag
   - If it's the latest major piece, update the "Featured" section

4. **Commit and push**
   ```bash
   git add .
   git commit -m "Add article: <title>"
   git push origin main
   ```

5. **Verify on GitHub Pages**
   - Changes deploy automatically within 1-2 minutes
   - Check live URL: https://eugene-burachevskiy.github.io/ai-vs-devops-blog/
   - Validate OG tags with https://www.opengraph.xyz/

### Required Meta Tags for Every Article

Every article **must** include the following in `<head>`:

**1. Favicon (browser tab icon):**
```html
<link rel="icon" type="image/jpeg" href="../images/favicon.jpg">
```

**2. OpenGraph tags (for link previews in Telegram, Facebook, LinkedIn, Slack, Discord):**
```html
<meta property="og:type" content="article">
<meta property="og:url" content="https://eugene-burachevskiy.github.io/ai-vs-devops-blog/articles/<slug>.html">
<meta property="og:title" content="Article Title">
<meta property="og:description" content="Short description for previews">
<meta property="og:image" content="https://eugene-burachevskiy.github.io/ai-vs-devops-blog/images/<article-image>.jpg">
```

**3. Twitter Card tags (for Twitter/X previews):**
```html
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="Article Title">
<meta name="twitter:description" content="Short description for previews">
<meta name="twitter:image" content="https://eugene-burachevskiy.github.io/ai-vs-devops-blog/images/<article-image>.jpg">
```

**OG image requirements:**
- Minimum 1200x630px for optimal display across all platforms
- Use `.jpg` or `.png`
- Place in `/images/` directory
- Use absolute URLs (not relative paths) for `og:image` and `twitter:image`

### Article Slug Convention
- Use kebab-case: `advanced-llm-ai-engineering-may-2026.html`
- Include date or version identifier for time-sensitive technical content
- Keep under 60 characters for SEO

### Category Badges
Available categories (match existing badge colors):
- `AI Tools & Automation` — blue
- `AI-Assisted Development` — purple
- `Infrastructure as Code` — orange
- `AI Development Methodology` — cyan
- `AI Engineering` — green
- `DevOps` — red

---

## 6. Key Constraints

- **Static HTML only** — No build step, no frameworks, no server-side rendering
- **Self-contained articles** — Each article is a standalone HTML file with inline `<style>` (copied from template)
- **No external dependencies** beyond Google Fonts and images
- **Dark theme is the only theme** — No light mode support
- **GitHub Pages hosting** — All content must be static and served from the repo

---

## 7. Article Template Reference

When creating new articles, base them on the structure from existing articles like `advanced-llm-ai-engineering-may-2026.html` or `telegram-notifications-claude-opencode.html`. Key structural elements:

```html
<!DOCTYPE html>
<html lang="en">  <!-- or "ru" for Russian -->
<head>
    <meta charset="UTF-8">
    <link rel="icon" type="image/jpeg" href="../images/favicon.jpg">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Article Title</title>
    <!-- OpenGraph and Twitter Card meta tags -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">
    <style>
        /* Copy CSS variables and base styles from existing article */
    </style>
</head>
<body>
    <!-- Hero section with back button, badge, title, meta -->
    <!-- Main content with sections -->
    <!-- Footer -->
</body>
</html>
```

---

*Last updated: May 2026*
