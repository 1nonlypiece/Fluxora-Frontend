# Component guidelines

Use these conventions for new files under `src/components/`.

## Styling

- Prefer a component's existing CSS module or colocated stylesheet.
- Use the design tokens from `src/design-tokens.css` for colors, spacing,
  typography, radii, and motion.
- Keep responsive rules beside the component that owns the layout.
- Do not add a one-off color or spacing value when a token expresses the same
  intent.

## Component boundaries

- Keep data fetching in the relevant API hook or service, not in presentational
  components.
- Pass stable callbacks and data through props when a child does not need app
  context.
- Reuse shared primitives such as `VirtualList`, `EmptyState`, and the wallet
  provider before adding a parallel implementation.

## Accessibility

- Give every interactive control an accessible name and keyboard behavior.
- Use semantic headings, lists, and buttons before reaching for generic `div`s.
- Connect validation text with `aria-describedby` and expose blocking errors
  with `role="alert"`.
- Add or update a focused test for loading, empty, error, and success states
  when a component owns those states.

## Review checklist

Before opening a PR, run the focused component tests, `npm run lint`, and
`npm run build`. Keep unrelated refactors out of the same change.
