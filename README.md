# tools

A collection of single-file HTML tools for various purposes.

## Tools Index

- `gemini-image-editor.html` - Edit and transform images using Gemini 3 Pro via OpenRouter API
- `hn-best-comments.html` - View and sort Hacker News best comments with auto-refresh
- `hn-thread-comments.html` - View top 5 comments from specific Hacker News threads
- `html-viewer.html` - View HTML source code of any webpage with syntax highlighting and comment extraction
- `openrouter-chat.html` - Chat with various LLM models via OpenRouter API with streaming responses
- `svg-viewer.html` - Preview SVG code with real-time rendering and sample templates

## How to Create New Tools

Use this template when creating new HTML tools for this repository:

```
Create a single-file HTML tool for [PURPOSE].

Requirements:
- Single HTML file with inline CSS and JavaScript
- No React or build steps
- Load dependencies from CDN (cdnjs or jsdelivr) if needed
- Keep it under 400 lines if possible
- Responsive design for mobile
- Save the file as [tool-name].html (use kebab-case)

Specific functionality:
[DESCRIBE FEATURES]

Style preferences:
- Clean, minimal UI
- Mobile-friendly with good tap targets
- Modern CSS (flexbox/grid)
- Appropriate color scheme

After creating the tool:
1. Create [tool-name].docs.md with documentation
2. Update README.md index
3. Test on mobile and desktop
```

### File Naming Rules

- Use kebab-case (lowercase with hyphens)
- Keep names descriptive but concise
- HTML files: `[tool-name].html`
- Documentation: `[tool-name].docs.md`

## Usage

All tools are standalone HTML files. Simply open them in a web browser - no server or build process required.
