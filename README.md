
# Trego Analytics Website

This is a static website for Trego Analytics, built with HTML, TailwindCSS, and minimal JavaScript. It is designed for personal/portfolio use and is not a full web application.

## How it Works

- **Static HTML**: All pages are plain HTML files (see `index.html`, `index2.html`, `post.html`, etc.).
- **Styling**: Uses TailwindCSS for all styling. Custom styles are in `assets/styles/main.css` and compiled/minified to `main.min.css`.
- **Assets**: Images and icons are in `assets/img/`. No fonts or JS frameworks are bundled.
- **JavaScript**: No custom JS logic is present (`assets/js/main.js` is empty). Alpine.js and tw-elements are loaded via CDN for minor interactivity (e.g., mobile menu, transitions).
- **Build Tools**: Uses PostCSS and TailwindCSS via npm/yarn scripts. BrowserSync is used for local development/live reload.

## Development

1. Install dependencies: `yarn install` (or `npm install`)
2. Start local server with live reload: `yarn develop`
3. Build production CSS: `yarn build`

**Note:** Node.js 12.13+ is required.

## Structure

- `index.html`, `index2.html`, etc.: Main site pages
- `assets/styles/`: Tailwind source and compiled CSS
- `assets/img/`: Images and SVGs
- `assets/js/`: (Empty, reserved for future JS)
- `package.json`: Build scripts and dependencies
- `postcss.config.js`, `tailwind.config.js`: Build and Tailwind config
- `browser-sync-config.js`: Local dev server config

## Deployment

Just upload the HTML and `assets/` folder to any static web host (e.g., GitHub Pages, Netlify, Vercel).

---

## High-Level Suggestions for Improvement

- **Modernize Build**: Upgrade Tailwind, PostCSS, and dependencies to latest versions.
- **Remove Unused JS**: Delete empty JS files and any unused dependencies.
- **Componentize**: Use a static site generator (e.g., Eleventy, Astro) for reusable layouts/components.
- **Accessibility**: Audit and improve accessibility (semantic HTML, ARIA, color contrast).
- **Performance**: Optimize images, use modern formats (WebP/SVG), and add lazy loading.
- **SEO**: Improve meta tags, canonical URLs, and add sitemap/robots.txt.
- **Content Management**: Consider a headless CMS or markdown for easier content updates.
- **Testing**: Add automated checks for broken links, accessibility, and performance.

Let’s say you want to keep the `fontFamily` classes Tailwind has, here’s how you could change the config to make it happen:

**Original**

```js
// tailwind.config.js
module.exports = {
	...
	theme: {
	        fontFamily: {
	            header: [ "Merriweather", "serif"],
	            body: ["Poppins", "sans-serif"]
	        },
	}
	...
}
```

**Keep the Tailwind defaults**

```js
// tailwind.config.js
module.exports = {
	...
	theme: {

	},
	extend: {
			fontFamily: {
	            header: [ "Merriweather", "serif"],
	            body: ["Poppins", "sans-serif"]
	        },
	}
	...
}
```

That’s it, next time you compile, you’ll have the `font-sans`, `font-serif` and `font-mono` classes available.
