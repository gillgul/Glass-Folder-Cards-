# Glass Folder Cards

A folder you can actually use, drawn as an object: a back panel with generated
artwork, real file cards, and a frosted-glass front panel that leans toward you
on hover, opens on click, and takes new files with `+`.

The component comes in two forms.

## 1. Standalone HTML + JavaScript (no install)

Everything is in one file: [`standalone/glass-folder-cards.html`](standalone/glass-folder-cards.html)
(HTML, CSS and plain JavaScript, no libraries).

- Double-click the file to open it in a browser, or
- serve it with Python and open it automatically:

```bash
python standalone/serve.py
```

Use it in your own page:

```js
const folder = createGlassFolder({ label: "Projects", art: "dusk", action: "add" })
document.body.append(folder)
```

## 2. React component (Next.js + shadcn + Tailwind + TypeScript)

- Component: [`components/ui/glass-folder-cards.tsx`](components/ui/glass-folder-cards.tsx)
- Demo: [`components/glass-folder-cards-demo.tsx`](components/glass-folder-cards-demo.tsx), shown on [`app/page.tsx`](app/page.tsx)

```bash
npm install
npm run dev
```

Then open http://localhost:3000.

```tsx
import GlassFolder from "@/components/ui/glass-folder-cards"

<GlassFolder label="My Files" art="aurora" files={[{ name: "Brief.pdf", meta: "PDF · 1.2 MB" }]} />
```

## Options

| Prop | Values | Default |
|---|---|---|
| `label` | text | `"My Files"` |
| `meta` | text (defaults to the file count) | — |
| `tone` | `"light"` / `"dark"` | `"light"` |
| `art` | `"aurora"`, `"ember"`, `"dusk"`, `"glacier"`, `"verdant"`, a custom recipe, or `"none"` | `"aurora"` |
| `image` | your own picture for the back panel | — |
| `files` | `{ name, meta?, art?, image?, href? }[]` | 3 sample files |
| `action` | `"add"` / `"more"` / `"none"` | `"add"` |
| `menu` | `{ label, onSelect?, danger? }[]` for `action: "more"` | `[]` |
| `labelPlacement` | `"bottom-left"` / `"top-left"` / `"top-right"` | `"bottom-left"` |
| `width` | px (height scales with it) | `340` |
| `onAdd`, `onFilesChange`, `onOpenChange`, `onFileSelect` | callbacks | — |
