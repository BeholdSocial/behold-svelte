# The Official Behold Widget for Svelte

[![Behold](https://img.shields.io/badge/Behold-e8ebd7.svg?style=for-the-badge&logo=data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0idXRmLTgiPz4KPCEtLSBHZW5lcmF0b3I6IEFkb2JlIElsbHVzdHJhdG9yIDI2LjMuMSwgU1ZHIEV4cG9ydCBQbHVnLUluIC4gU1ZHIFZlcnNpb246IDYuMDAgQnVpbGQgMCkgIC0tPgo8c3ZnIHZlcnNpb249IjEuMSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB4bWxuczp4bGluaz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94bGluayIgeD0iMHB4IiB5PSIwcHgiCgkgdmlld0JveD0iMCAwIDI1IDI1IiBlbmFibGUtYmFja2dyb3VuZD0ibmV3IDAgMCAyNSAyNSIgeG1sOnNwYWNlPSJwcmVzZXJ2ZSI+CjxwYXRoIGZpbGw9IiMzY2E1NjYiIGQ9Ik0xMi41LDYuOGMwLjgsMCwxLjgsMC4xLDIuOCwwLjNjMS4zLDAuMywyLjQsMS4zLDIuNiwyLjZjMC4yLDEsMC4zLDEuOSwwLjMsMi44YzAsMC45LTAuMSwxLjktMC4zLDIuOQoJYy0wLjMsMS4zLTEuMywyLjMtMi42LDIuNmMtMSwwLjItMiwwLjQtMi44LDAuNGMtMC45LDAtMS45LTAuMS0zLTAuNGMtMS4xLTAuMy0yLTEuMi0yLjMtMi4zYy0wLjMtMS4xLTAuNC0yLjEtMC40LTMKCWMwLTAuOCwwLjEtMS44LDAuMy0yLjhjMC4zLTEuMywxLjMtMi40LDIuNi0yLjZDMTAuNyw2LjksMTEuNyw2LjgsMTIuNSw2LjggTTEyLjUsMC41Yy0xLjQsMC0yLjgsMC4yLTQsMC41QzQuNywxLjcsMS44LDQuNiwxLDguNAoJYy0wLjMsMS4zLTAuNSwyLjctMC41LDQuMWMwLDEuNiwwLjIsMy4xLDAuNiw0LjVjMC44LDMuNCwzLjUsNi4xLDYuOSw3YzEuNCwwLjMsMi45LDAuNiw0LjUsMC42YzEuNSwwLDIuOS0wLjIsNC4yLTAuNQoJYzMuNy0wLjgsNi41LTMuNyw3LjMtNy40YzAuMy0xLjMsMC41LTIuNywwLjUtNC4yYzAtMS40LTAuMi0yLjgtMC40LTRjLTAuOC0zLjgtMy43LTYuNi03LjUtNy40QzE1LjMsMC43LDEzLjksMC41LDEyLjUsMC41CglMMTIuNSwwLjV6Ii8+Cjwvc3ZnPgo=)](https://behold.so)
![Svelte](https://img.shields.io/badge/svelte-%23f1413d.svg?style=for-the-badge&logo=svelte&logoColor=white)

## About

This package contains a Svelte version of the [Behold embedded widget](https://behold.so/docs/widget/). It's a lightweight convenience wrapper around the core Behold widget web component, and allows easy integration into your Svelte projects.

## Installation

Start by installing with your package manager of choice:

```jsx
npm install @behold/svelte

// or
pnpm add @behold/svelte

// or
yarn add @behold/svelte
```

## Usage

### 1. Import the component

```js
import BeholdWidget from "@behold/svelte"
```

### 2. Add to your app

Use it like you would any other Svelte component:

```html
<BeholdWidget feedId="YOUR_FEED_ID" />
```

The Behold widget component accepts a single property: `feedId`, which can be found by opening your feed in the [Behold dashboard](https://app.behold.so) and clicking on "Embed Code".

All configuration and customization is handled in the Behold admin. When you make changes there it will automatically update your widget, no code modifications required. Because of browser caching, changes can take a minute or two to show up. Clearing your cache and incognito/private windows will help.

![Behold feed settings page](./readme-images/find-your-feed-id-1.png)
![Behold feed embed code page](./readme-images/find-your-feed-id-2.png)

## Load event

This component emits a load event after its initial render. It can be used as follows:

```js
<BeholdWidget on:load={() => console.log("Loaded!")} feedId="YOUR_FEED_ID" />
```

## A note about SSR

Because these widgets are inherantly dynamic in nature, they are client-side only, and won't be pre-rendered by SSR or SSG. That means there will be a moment before they render that their height will be 0px. You can prevent layout shifts this may cause by applying dimensions to a container element with CSS.

## Other framework components

[![React](https://img.shields.io/badge/react-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB)](https://www.npmjs.com/package/@behold/react)
[![Preact](https://img.shields.io/badge/preact-%2320232a.svg?style=for-the-badge&logo=preact&logoColor=%23ae80ff)](https://www.npmjs.com/package/@behold/preact)
[![Vue.js](https://img.shields.io/badge/vuejs-%2335495e.svg?style=for-the-badge&logo=vuedotjs&logoColor=%234FC08D)](https://www.npmjs.com/package/@behold/vue)
[![Angular](https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white)](https://www.npmjs.com/package/@behold/angular)
