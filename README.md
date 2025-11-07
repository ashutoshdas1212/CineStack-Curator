CineStack Curator





https://user-images.githubusercontent.com/70796875/221602490-15893fc2-81e7-4fe7-90c4-02cd45f2ff34.mp4






## Basic Features

1. List of Movies with their IMDB rating
2. Search Bar
3. Add Another Movies
4. Favourite/ Unfavourite Buttons
5. Seprate Favourite tab






A responsive React + Redux application to browse movies, search the OMDb catalogue, and curate a personal favourites list. Built with Create React App and deployed to GitHub Pages.

## Live

- App: http://ashutoshdas.github.io/movies-app
- Preview: https://user-images.githubusercontent.com/70796875/221602490-15893fc2-81e7-4fe7-90c4-02cd45f2ff34.mp4

## Features

- Curated catalogue with IMDb ratings and poster art
- Add/Remove favourites; dedicated Favourites tab
- Real-time OMDb search and one-click add to library
- Clear empty states and duplicate-prevention in favourites
- Mobile-friendly, responsive layout

## Tech Stack

- React 17, Redux, Redux Thunk, Context API (custom Provider)
- CSS with media queries (no UI framework)
- Tooling: `react-scripts`, `gh-pages`
- API: OMDb (`https://www.omdbapi.com`)

## Project Structure

```
src/
  actions/        Redux action creators + thunks (OMDb)
  components/     App, Navbar, MovieCard (class components)
  reducers/       movies + search slices (combined)
  data.js         Seed dataset
  index.js        Store setup, middleware, custom Provider
  index.css       Global styles + responsive rules
```

## Getting Started

### Prerequisites

- Node.js 14+ and npm (or Yarn)
- OMDb API key (free: http://www.omdbapi.com/apikey.aspx)

### Install

```bash
git clone https://github.com/<your-username>/Favourite-Movies-master.git
cd Favourite-Movies-master
npm install
```

### Configure Environment

Create a `.env` file in the project root:

```bash
REACT_APP_OMDB_KEY=your_api_key_here
```

Update the API key usage in `src/actions/index.js` to read from the env variable before pushing public code:

```diff
- const url = `https://www.omdbapi.com/?apikey=205c172a&i=${id}`;
// replace with
  const url = `https://www.omdbapi.com/?apikey=${process.env.REACT_APP_OMDB_KEY}&i=${id}`;

- const url = `https://www.omdbapi.com/?i=tt3896198&apikey=205c172a&s=${movie}`;
// replace with
  const url = `https://www.omdbapi.com/?i=tt3896198&apikey=${process.env.REACT_APP_OMDB_KEY}&s=${movie}`;
```

### Run

```bash
npm start
# http://localhost:3000
```

### Scripts

- `npm start` – start dev server
- `npm run build` – production build
- `npm test` – run tests (Testing Library ready)
- `npm run deploy` – publish to GitHub Pages

## Deployment

This repo is configured for GitHub Pages via `gh-pages`. Ensure `homepage` in `package.json` points to your repo URL, then:

```bash
npm run deploy
```

## Notes

- Simple logger middleware logs action types for debugging
- State is client-side; favourites are not persisted across refreshes

## Roadmap

- Hooks refactor (`useSelector`, `useDispatch`)
- Loading/error states and pagination for search
- Persist favourites (localStorage or backend)
- Tests for reducers, thunks, and components
- CI with GitHub Actions (lint/test/build/deploy)

## Contributing

1. Fork the repo
2. Create a feature branch (`git checkout -b feature/your-change`)
3. Commit and push
4. Open a PR

## License

MIT — use and adapt for learning or portfolio purposes

## Acknowledgements

Data provided by OMDb API — `https://www.omdbapi.com`
``` /src/actions ``` - all Redux Actions creators

``` /src/components ``` - all react components

``` /src/reducers ``` - all Redux reducers

```src/data.js ``` - static movies data
