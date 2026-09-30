# Ultraverse

An NFT marketplace UI rebuilt from a static template into a data-driven React app. Every collection, item, and seller loads from a live API, with custom skeleton loading states and carousel-driven browsing.

**[View the live site →](https://nft-market-ten-omega.vercel.app/)**

![Ultraverse home page](./screenshot.png)

## About the project

Ultraverse started as a static marketplace template with hard-coded content. I turned it into a working React app that fetches all of its data from an API, handles loading states cleanly, and routes to dynamic pages for individual items and authors. I built it as part of Frontend Simplified's frontend program.

## Features

- **Live API data:** collections, items, and sellers are fetched with Axios instead of hard-coded
- **Carousels:** browse hot collections and new items in responsive carousels
- **Skeleton loading states:** every data-driven section shows a placeholder shaped like its final layout while data loads
- **Dynamic routing:** item and author pages are generated from URL parameters with React Router <!-- TODO: confirm -->
- **Countdown timers and filtering:** live countdowns on items and sorting on the Explore page <!-- TODO: confirm -->
- **Scroll animations:** sections animate into view with AOS

## Key technical decision

I built skeleton loaders that match each component's final layout instead of using a generic spinner. The page holds its shape while data loads, so content doesn't jump around when the API responds. That's a better experience for users, and it avoids layout shift, which is one of Google's Core Web Vitals.

## Tech stack

- React
- React Router
- Axios
- Owl Carousel
- AOS (Animate On Scroll)
- Bootstrap
- Deployed on Vercel

## Running locally

```bash
git clone https://github.com/brenthippler-art/nft-market.git
cd nft-market
npm install
npm start
```

The app runs at http://localhost:3000.

## Credits

Image credits are listed in [image-credits.txt](./image-credits.txt).

## Author

**Brenton Hippler:** [Portfolio](https://brentoncodes.dev) · [LinkedIn](https://www.linkedin.com/in/brenton-hippler-818b6397) · [GitHub](https://github.com/brenthippler-art)