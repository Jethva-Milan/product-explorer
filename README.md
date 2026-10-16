# Product Explorer

A responsive product browsing app built with **React**, **TypeScript** and **CSS** (powered by Vite).



## Features

- Product cards showing image, name, brand, price, rating and category
- Search products by name (debounced)
- Filter by category
- Sort by price: low to high or high to low
- Friendly message when no products match the search or filters
- Fully responsive layout for mobile, tablet and desktop
- Reusable components, custom React hooks and strict TypeScript types

## Tech Stack

- React 18
- TypeScript
- Vite
- Plain CSS

## Getting Started

### Prerequisites

- Node.js 18 or newer
- npm (comes with Node.js)

### Installation

```bash
git clone https://github.com/<your-username>/product-explorer.git
cd product-explorer
npm install
```

### Run in development

```bash
npm run dev
```

Open the URL shown in the terminal (usually http://localhost:5173).

### Build for production

```bash
npm run build
npm run preview
```

## Project Structure

```
src/
├── components/
│   ├── CategoryFilter.tsx   # Category pill buttons
│   ├── EmptyState.tsx       # "No products match" message
│   ├── ProductCard.tsx      # Single product card
│   ├── ProductGrid.tsx      # Responsive grid of cards
│   ├── ProductImage.tsx     # Image with loading state and fallback
│   ├── SearchBar.tsx        # Search input
│   ├── SortSelect.tsx       # Price sort dropdown
│   └── StarRating.tsx       # Star rating display
├── hooks/
│   ├── useDebouncedValue.ts # Generic debounce hook
│   └── useProductFilters.ts # Search, category and sort logic
├── data/
│   └── products.ts          # Mock product data
├── types.ts                 # Shared TypeScript types
├── App.tsx
├── App.css
└── main.tsx
```

## Design Decisions

- **Filtering logic lives in a custom hook** (`useProductFilters`), keeping `App.tsx` a thin layer and making the logic easy to test.
- **Derived data uses `useMemo`**, so the visible list is only recalculated when the search, category or sort changes.
- **Category types come from one constant** (`CATEGORIES`), so the type and the filter buttons can never drift apart.
- **Sorting copies the array first**, so the original data is never mutated.
- **Accessibility:** labelled inputs, `aria-pressed` on filter buttons, live region for the result count, visible focus styles and reduced-motion support.
- **Image fallback:** if a photo fails to load, the card shows a category illustration instead of a broken image.

## Possible Improvements

- Unit tests for `useProductFilters` (Vitest + React Testing Library)
- Price range filter
- Persist filters in the URL query string
- Product detail view
- Pagination or infinite scroll

## Author

Milan Jethva
