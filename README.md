# Apex Predator

**OWN THE TRACK. RULE THE RACE.**

Apex Predator is a responsive, React-based Formula 1 motorsport information and analytics platform developed to provide racing enthusiasts with a centralized environment for exploring drivers, constructors, circuits, race schedules and championship statistics. The application incorporates interactive features such as driver comparisons, personalized favourites, race countdowns, championship leaderboards and statistical visualizations. Developed using HTML5, CSS3, JavaScript and React.js, the platform demonstrates modern frontend development practices through component-based architecture, dynamic rendering, responsive interfaces and interactive data presentation.

> Independent educational fan project. Not affiliated with Formula 1, the FIA, or any racing team.

## Features

- Premium responsive race command centre with championship snapshot, event panel and data visualizations.
- Driver directory with text search, constructor and nationality filters, sorting, profiles and local favourites.
- Constructor standings and team detail pages.
- Circuit explorer with schematic track maps and track facts.
- Full 24-round 2024 calendar with event detail routes.
- Driver and constructor championship tables.
- Driver head-to-head comparison and interactive Recharts visualizations.
- Global keyboard-search dialog (`Ctrl/Cmd + K`), light/dark theme preference and persistent garage.
- Accessible labels, keyboard focus styles, responsive layouts and not-found route.

## Technology

React 18, JavaScript/JSX, Vite, React Router DOM, Lucide React, Recharts, Framer Motion, CSS3 and localStorage. No backend or external API is required to run the app.

## Structure

```text
src/
  App.jsx       Routing, shared layout, page components and interactions
  data.js       Bundled driver, team, circuit, schedule and chart data
  main.jsx      React/Vite entry point
  styles.css    Responsive design system and page styles
index.html      App shell, metadata and font loading
vercel.json     SPA route rewrite for Vercel
vite.config.js  Vite configuration
```

## Run locally

Requirements: Node.js 18+ and npm.

```bash
npm install
npm run dev
```

Open the local URL printed by Vite. Create a production bundle with `npm run build`; inspect it using `npm run preview`.

## Data and accuracy notes

The bundled championship figures and calendar represent the **2024 season**. Driver and constructor championship totals are final 2024 totals. The chart preview includes representative early-season round data, not a complete per-round feed. The calendar contains each event's date, venue and winner, but does not include full session classifications. The circuit explorer intentionally contains a small curated set of circuits; track diagrams are original schematic SVG paths and are not official FIA drawings. As no live API is connected, the home race panel correctly presents the archived season as complete rather than inventing an upcoming event or live countdown. Verify any statistics against official championship records before relying on them for publication.

The visual hero uses a motorsport photo by Samuel Phillips on Pexels (free photo, `https://www.pexels.com/photo/red-formula-1-racing-car-on-track-action-shot-30205195/`) with a dark overlay. If unavailable, the page retains its CSS background treatment. Google Fonts are loaded remotely with local system fallbacks.

## Components and implementation notes

- `App` owns global UI state (favourites, theme, search, mobile navigation) and declares React Router routes.
- `DriverCard`, `SectionTitle`, `PageTitle`, and `Track` are reusable presentation components.
- `DriversPage` composes search/filter/sort state and filters the local driver array without a server.
- `ChampChart` and the comparison/analytics pages use Recharts responsive charts.
- Favourites and theme preferences use React state synchronized to `localStorage`.
- `SearchDialog` searches drivers, constructors, circuits, and races, and supports `Ctrl/Cmd + K` and Escape.
- Profile routes resolve slugs against the local dataset and show the not-found page for unknown records.

## GitHub

Create an empty repository on GitHub, then from this directory run:

```bash
git add .
git commit -m "Build Apex Predator F1 analytics app"
git branch -M main
git remote add origin https://github.com/USERNAME/REPOSITORY.git
git push -u origin main
```

Replace `USERNAME/REPOSITORY` with your repository path. No remote repository was configured or pushed by this project setup.

## Vercel deployment

1. Import the GitHub repository in Vercel.
2. Keep the Vite defaults: build command `npm run build`, output directory `dist`.
3. Deploy. `vercel.json` rewrites nested SPA paths to `index.html`, so direct links and refreshes resolve through React Router.

For a CLI deployment, install/authenticate the Vercel CLI and run `vercel` from the project directory, then `vercel --prod` when ready. No deployment has been published from this workspace.

## Screenshots

Add screenshots here after running the app, for example:

```md
![Race command centre](docs/screenshots/home.png)
```

## License and credits

Educational fan project. Formula 1 and related marks belong to their respective owners. Hero photo credit: Samuel Phillips / Pexels. Google Fonts serves the typefaces when network access is available. Data is a bundled historical demonstration snapshot; consult official sources for authoritative records.
