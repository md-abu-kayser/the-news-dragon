# The News Dragon - Fast React + Vite News Client

<!-- MIT License -->

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](./LICENSE)

<!-- HTML & CSS -->

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)

<!-- Styling / PostCSS -->

[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?logo=tailwindcss&logoColor=white)](https://tailwindcss.com/docs/)
[![PostCSS](https://img.shields.io/badge/PostCSS-efefef?logo=postcss&logoColor=black)](https://postcss.org/)

<!-- Languages & Web Standards -->

[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![ECMAScript Spec](https://img.shields.io/badge/ECMAScript-262-7A0BC0?logo=ecmascript&logoColor=white)](https://www.ecma-international.org/publications-and-standards/standards/ecma-262/)
[![TypeScript](https://img.shields.io/badge/TypeScript-3178c6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/docs/)

<!-- Infra & Runtime -->

[![Node.js](https://img.shields.io/badge/Node.js-339933?logo=node.js&logoColor=white)](https://nodejs.org/)
[![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://react.dev/)

<!-- Linting & Formatting -->

[![ESLint](https://img.shields.io/badge/ESLint-4B32C3?logo=eslint&logoColor=white)](https://eslint.org/docs/latest/)
[![Prettier](https://img.shields.io/badge/Prettier-2B3A42?logo=prettier&logoColor=white)](https://prettier.io/docs/)

<!-- Bundler -->

[![Vite](https://img.shields.io/badge/Vite-646cff?logo=vite&logoColor=white)](https://vite.dev/)


## Plain docs links

- HTML (MDN) docs: [https://developer.mozilla.org/en-US/docs/Web/HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)
- CSS (MDN) docs: [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
- Tailwind CSS docs: [https://tailwindcss.com/docs/](https://tailwindcss.com/docs/)
- PostCSS docs / postcss.config: [https://postcss.org/](https://postcss.org/)
- JavaScript (MDN) docs: [https://developer.mozilla.org/en-US/docs/Web/JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
- ECMAScript (spec, ECMA-262) docs: [https://www.ecma-international.org/publications-and-standards/standards/ecma-262/](https://www.ecma-international.org/publications-and-standards/standards/ecma-262/)
- TypeScript docs: [https://www.typescriptlang.org/docs/](https://www.typescriptlang.org/docs/)
- Node.js docs: [https://nodejs.org/](https://nodejs.org/)
- React docs: [https://react.dev/](https://react.dev/)
- ESLint docs: [https://eslint.org/docs/latest/](https://eslint.org/docs/latest/)
- Prettier docs: [https://prettier.io/docs/](https://prettier.io/docs/)
- Vite docs: [https://vite.dev/](https://vite.dev/)

---

A modern, responsive news client built with React, Vite and TypeScript. This project demonstrates a clean component-driven architecture, route-based data loading, Tailwind + Bootstrap styling, and Firebase integration scaffolding - ideal as a portfolio piece or production starter for news-style applications.

## Live Preview

Run locally with Vite (instructions below) to preview the app during development.

---

## Highlights and Features

- Fast development with Vite and React 18
- Type-safe components and shared types (see [`src/types/News.ts`](src/types/News.ts) and [`src/types/Category.ts`](src/types/Category.ts))
- Route-driven data loaders with React Router v6 (see [`router`](src/routes/Routes.tsx))
- Reusable UI: custom rating component [`CustomRating`](src/components/Rating/CustomRating.tsx)
- Responsive layouts: [`layouts/Main.tsx`](src/layouts/Main.tsx) and [`layouts/NewsLayout.tsx`](src/layouts/NewsLayout.tsx)
- Authentication provider scaffold: [`AuthProvider`](src/providers/AuthProvider.tsx)
- Firebase initializer for future auth/storage: default export `app` in [`src/firebase/firebase.config.ts`](src/firebase/firebase.config.ts)
- Tailwind + Bootstrap for flexible design system (`tailwind.config.js`, Bootstrap CSS import)

---

## Tech Stack

- Vite (`vite.config.ts`)
- React 18 + TypeScript (`tsconfig.json`)
- React Router v6 (`src/routes/Routes.tsx`)
- Tailwind CSS + Bootstrap
- Firebase (client initialization) (`src/firebase/firebase.config.ts`)
- React-Bootstrap, React-Icons, moment, react-fast-marquee

## Key files:

- Project config: [package.json](package.json), [vite.config.ts](vite.config.ts), [tailwind.config.js](tailwind.config.js)
- App entry: [`src/main.tsx`](src/main.tsx)
- Routing: [`src/routes/Routes.tsx`](src/routes/Routes.tsx)
- Core provider: [`src/providers/AuthProvider.tsx`](src/providers/AuthProvider.tsx)
- Types: [`src/types/News.ts`](src/types/News.ts), [`src/types/Category.ts`](src/types/Category.ts)
- Example UI: [`src/pages/Home/NewsCard/NewsCard.tsx`](src/pages/Home/NewsCard/NewsCard.tsx), [`src/components/Rating/CustomRating.tsx`](src/components/Rating/CustomRating.tsx)

---

## Getting Started (Developer)

1. **Clone the repo:**

```bash
   git clone https://github.com/md-abu-kayser/news-dragon-client.git

```

2. **Install:**

```
   npm install

```

3. **Development:**

```bash
   npm run dev

```

- App runs on the configured Vite port (see [vite.config.ts](vite.config.ts))

4. **Type-check:**

```
   npm run type-check

```

5. **Build:**

```bash
   npm run build

```

- Scripts live in: [package.json](package.json)

---

## Data and API

**Routes in [`src/routes/Routes.tsx`](src/routes/Routes.tsx) use loader fetches like:**

- GET http://localhost:5000/news/
- GET http://localhost:5000/news/:id
- GET http://localhost:5000/categories

These endpoints are expected from your backend. Adapt URLs or environment variables as needed.

---

## Architecture Notes

- route loaders provide server data to pages via `useLoaderData()` (see [`Category`](src/pages/Home/Category/Category.tsx) and [`News`](src/pages/News/News/News.tsx))
- `AuthProvider` centralizes auth state for the UI (`NavigationBar` uses it to render user icon)
- Types (`News`, `Category`) ensure consistent data shapes across components

---

### Recommended Improvements

- Move backend URLs to environment variables (Vite `.env`).
- Implement real Firebase Auth flows in [`AuthProvider`](src/providers/AuthProvider.tsx).
- Add unit and integration tests (React Testing Library + Vitest).
- Add CI workflow to run linting and type-checks.

---

## Contributing

Contributions welcome - follow standard PR workflow, keep commits focused, and add tests for new features.

---

### License

- This project is licensed under the terms of the **[MIT License](./LICENSE)**.
- You may replace or update the license as needed for client or proprietary projects.

---

### Contact & Maintainer

- **Project:** _news-dragon-client_
- **Name:** Md Abu Kayser - Full-Stack Engineer
- **Maintainer:** [md-abu-kayser](https://github.com/md-abu-kayser)
- **Email:** [abu.kayser.official@gmail.com](mailto:abu.kayser.official@gmail.com)
- **GitHub:** [github.com/abu.kayser-official](https://github.com/md-abu-kayser)

If you’d like this README tailored for a specific purpose - such as **hiring managers**, **open-source contributors**, or **client deliverables** - feel free to request a custom tone or format.

**Thank you for reviewing this project!**

---
