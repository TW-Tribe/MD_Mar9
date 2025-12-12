# What is CSH links?

## Summary

"CSH links" refers to Context‑Sensitive Help links — hyperlinks or UI hooks that open help content specifically relevant to the current screen, control, or user task. They let users get targeted assistance without searching a full help system.

## Why use CSH links?

- Reduce context switching: users get help relevant to what they're doing.
- Improve discoverability of documentation for complex UIs.
- Lower support load by surfacing inline guidance and examples.

## How CSH links work (conceptually)

A CSH link is associated with a context identifier (page, component id, or topic key). When activated it opens a help resource scoped to that identifier — e.g., a modal, a side panel, a new page anchored to a topic, or a tooltip. The mapping between context id and help content can be static (URL fragments) or dynamic (lookup table or API).

## Implementation patterns

- HTML fragment links: use anchors that point to a documentation page with a fragment, e.g. `/help/forms#field-validation`.
- Data-driven links: add `data-help-id` attributes and a small JS handler that resolves the id to a URL or content and displays it in a modal.
- Desktop apps: attach help context ids to controls and use the platform help API to open the correct topic.

### Simple HTML example

```html
<!-- link pointing to a help topic fragment -->
<a href="/help/getting-started#creating-account" class="csh-link">Help</a>
```

### Data-driven example (web)

```html
<button data-help-id="profile-edit" class="help-btn">Help</button>
```

```javascript
document.addEventListener('click', (e) => {
	const btn = e.target.closest('[data-help-id]');
	if (!btn) return;
	const id = btn.getAttribute('data-help-id');
	// map id -> URL or fetch content
	const url = `/help/topics/${id}.html`;
	openHelpModal(url);
});
```

## Accessibility and UX considerations

- Use clear, descriptive link text (avoid just "Help").
- Ensure keyboard focus moves into the help panel and back when closed.
- Provide skip/back links so users can return to their task.
- Announce opening/closing of help panels to screen readers.

## Best practices

- Keep help short and task-oriented; link to deeper docs for advanced topics.
- Maintain stable context ids so links don't break when content moves.
- Track which CSH topics are used most to improve docs and UI affordances.

## Common pitfalls

- Linking to long, generic pages — defeats the point of context sensitivity.
- Relying solely on client-side JS without fallback URLs for crawlers and plain links.

## Testing

- Verify each `data-help-id` resolves to the correct content.
- Test keyboard-only and screen-reader navigation.
- Validate links work when the app is served from different base paths.

## Further reading

- Topic-based help design patterns
- Accessibility guidelines for dialogs and modals

---

Add examples or product-specific mappings here as needed.

## Product-specific examples (this site)

Below are small, practical examples tailored for this site's structure. The site uses simple permalinks (`/freelance/`, `/portfolio/`, `/resume/`) and chapter files under `Chapters/`.

1) Simple permalink (Jekyll) link to a help topic:

```html
<a href="/freelance/">Freelance services — Help</a>
```

2) Anchor fragment to a section inside a chapter:

```html
<a href="/Chapters/Chapter1_Basics/Intro.md#lesson-2">Field help: Lesson 2</a>
```

3) Data-driven CSH button (open topic or modal):

```html
<button data-help-id="chapter:portfolio" class="help-btn">Need help with projects</button>
```

```javascript
// Minimal resolver for this static site
const helpMap = {
	'chapter:intro': '/Chapters/Chapter1_Basics/Intro.md',
	'chapter:portfolio': '/portfolio/',
	'chapter:freelance': '/freelance/',
	'chapter:resume': '/resume/'
};

document.addEventListener('click', (e) => {
	const btn = e.target.closest('[data-help-id]');
	if (!btn) return;
	const id = btn.getAttribute('data-help-id');
	const url = helpMap[id];
	if (!url) return;
	// Prefer modal display; fallback to opening a new tab
	if (typeof openHelpModal === 'function') {
		openHelpModal(url);
	} else {
		window.open(url, '_blank');
	}
});
```

Notes:
- Use the Jekyll `permalink` (e.g., `/freelance/`) where available so links remain stable.
- For chapters stored as raw `.md` files, consider rendering the help fragment into HTML or linking to the rendered site path.

