
# Shopping Cart (Vite + React)

A small demo shopping-cart app built with React and Vite. It demonstrates a simple product listing, cart management, and a modal-based cart UI using React Context for state management. This README focuses on the app features, the main technical concepts used, and exact local setup steps so you can run the project quickly.

## Checklist (what I'll cover)

- Explain the app features
- List the main tech & concepts used
- Show the important files and structure
- Provide exact local setup and run instructions (zsh)

## Features

- Browse a static product catalog (images, title, price).
- Add products to the cart and adjust quantities.
- Remove items from the cart.
- View cart contents in a modal and review before checkout.
- Single shared cart state across components using React Context.

## Tech & Concepts Used

- React (v19) — functional components and hooks (useState, useContext).
- Vite — dev server, HMR, and fast production builds.
- React Context API — centralized cart state and actions (see `store/shopping-card-context.jsx`).
- Component-driven UI — components live in `src/components` (e.g., `Shop.jsx`, `Product.jsx`, `Cart.jsx`, `CartModal.jsx`, `Header.jsx`).
- Static data file — `src/dummy-products.js` provides product data used by the shop.
- ESLint — linting setup included; run via npm script.

## Project structure (high level)

- `index.html` — entry HTML for Vite.
- `package.json` — scripts and dependencies.
- `src/main.jsx` — React entry point.
- `src/App.jsx` — top-level layout.
- `src/components/` — UI components: `Shop.jsx`, `Product.jsx`, `Cart.jsx`, `CartModal.jsx`, `Header.jsx`.
- `src/dummy-products.js` — product catalog used by the app.
- `src/assets/` — product images used in the UI.
- `store/shopping-card-context.jsx` — cart state and actions (note the filename uses "card" in this project).

## Prerequisites

- Node.js (LTS recommended). Node 18+ is a good baseline.
- npm (bundled with Node) or an alternative package manager (yarn/pnpm). Instructions below use npm and zsh.

## Local setup (zsh)

Open a terminal in the project root and run the following commands.

```zsh
# 1) Install dependencies
npm install

# 2) Start the dev server (Vite). App will be available at http://localhost:5173 by default
npm run dev
```

Available npm scripts (from `package.json`):

```zsh
npm run dev     # start vite dev server (development)
npm run build   # build production bundle
npm run preview # preview production build locally
npm run lint    # run ESLint checks
```

Notes:
- If `npm run dev` fails because port 5173 is in use, Vite will suggest another port or you can free the port.
- To use `yarn` instead of `npm`:

```zsh
yarn install
yarn dev
```

## How the app works (quick overview)

- `src/dummy-products.js` exports the product list used by `Shop.jsx`.
- `Shop.jsx` maps the product list to `Product` components.
- `Product.jsx` has an "Add to cart" button that calls into the cart context actions.
- `store/shopping-card-context.jsx` exposes the cart state and methods via React Context so any component can read or update the cart.
- `Cart.jsx` and `CartModal.jsx` render the shared cart state and let users increment, decrement, or remove items.

## Development tips

- Run `npm run lint` regularly to catch accessibility and React lint issues.
- Add images to `src/assets` and import them from components for Vite to bundle them.
- Consider adding `localStorage` persistence in `store/shopping-card-context.jsx` to keep the cart between reloads.

## Troubleshooting

- "Command not found: npm" — install Node.js from https://nodejs.org/.
- Linting errors — run `npm run lint` and follow ESLint output to fix issues.
- Dev server network or port issues — try `npm run dev -- --port <port>` to pick a custom port.

## Next steps / Ideas

- Persist cart state to localStorage.
- Add product categories and search.
- Add unit tests (Jest + React Testing Library) and a CI pipeline.

---

Requirements coverage:
- Explain the features primarily — Done (Features section).
- Tech concepts used — Done (Tech & Concepts + How it works).
- Local setup instructions — Done (Practical zsh commands and scripts).

If you'd like, I can also:

- Add a short CONTRIBUTING.md or code-of-conduct.
- Add a small test for the cart reducer and run it.
