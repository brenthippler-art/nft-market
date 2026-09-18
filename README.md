# Ultraverse

An NFT marketplace front-end — live collection/item data, sortable and paginated browsing, author profiles, and scroll-triggered animation throughout.

🔗 [Live Demo](https://nft-market-ten-omega.vercel.app/)

## Features

- Hot Collections, New Items, and Top Sellers sections, each pulling live data from a REST API
- Explore page: sort by Default, Price (low→high / high→low), or Most Liked, with an initial 8 items and a "Load More" button that reveals 4 more at a time (up to 16) before disappearing
- Author and Item Detail pages driven by dynamic route params — one component template renders any author or item based on the URL
- Config-driven skeleton loading system (`SkeletonCarousel`, `SkeletonList`, `SkeletonGrid`) — one reusable set of loading components instead of a bespoke skeleton per section
- Scroll-triggered animations (AOS) throughout
- Fully responsive carousels and grids

## Tech Stack

React, React Router, Axios, Bootstrap, Owl Carousel (react-owl-carousel), AOS (Animate On Scroll)

## Notable Engineering Details

- Owl Carousel has a known issue re-initializing against data that loads asynchronously after mount (an `UNSAFE_componentWillReceiveProps` lifecycle conflict). Fixed by conditionally rendering the carousel only once its data has actually arrived, keyed so it fully remounts rather than trying to update in place.
- Built one config-driven skeleton loading system rather than one-off placeholder markup per section — a shape (carousel vs. list vs. grid) and item count in, matching skeleton tiles out, reused across every section that fetches data.
- Debugged a flex `min-width: auto` default that was silently preventing tiles from shrinking below their content size at narrow breakpoints, and a percentage-height chain that wouldn't resolve until every ancestor in the chain had an explicit height.
- Sort and pagination on the Explore page are driven by a single source of truth for the full fetched dataset — sorting re-derives the visible slice rather than re-fetching, and "Load More" just extends how much of that already-sorted list is rendered.

## Running Locally

```bash
git clone https://github.com/brenthippler-art/nft-market.git
cd nft-market
npm install
npm start
```

## Author

Brenton Hippler — Frontend Developer | [brentoncodes.dev](https://brentoncodes.dev)
