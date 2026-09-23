# Grid Layout

A simple CSS Grid page layout with a header, sidebar, two content sections, and a footer.

## Files

- `index.html` — page markup (six labeled boxes: HEADER, SIDEBAR, CONTENT1, CONTENT2, CONTENT3, FOOTER)
- `index.css` — grid layout and styling

## Layout

```
┌─────────────────────────────┐
│           HEADER             │
├─────────┬─────────────────────┤
│         │      CONTENT1       │
│ SIDEBAR ├───────────┬─────────┤
│         │ CONTENT2  │CONTENT3 │
├─────────┴───────────┴─────────┤
│           FOOTER             │
└─────────────────────────────┘
```

Built with a `.container` using `display: grid`:
- `grid-template-columns: 200px 1fr 1fr` — fixed sidebar, two flexible content columns
- `grid-template-rows: 80px 1fr 1fr 70px` — fixed header/footer heights, flexible middle rows
- Each box is placed explicitly with `grid-column` / `grid-row`, so nothing overlaps or falls back to implicit placement

On screens narrower than 640px, the layout switches to a single stacked column (see the `@media (max-width: 640px)` block in `index.css`).

## Usage

Open `index.html` in a browser. No build step or dependencies required.

## Customizing

- Colors are set directly on each `#ID` selector in `index.css` — change the `background` values to restyle.
- Adjust column/row sizes in `.container` to resize the sidebar, header, or footer.
- Add more boxes by giving them an id, placing them with `grid-column` / `grid-row`, and adding the corresponding `<div class="box" id="...">` in `index.html`.
