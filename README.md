# UX Principles Playground

Well-known UX principles, each with a small timed test you can try yourself.

Reading that "more options slow people down" is one thing. Watching your own time double when the menu goes from 6 items to 24 is another. Every principle here has two versions of the same task: version A breaks the principle, version B follows it. Try both and compare your times.

**Live demo:** https://jolanta-io.github.io/ux-laws-playground/

![Screenshot](screenshot.png)

## Principles included

| Principle | Origin | What you do |
|---|---|---|
| Fitts's Law | Paul Fitts, 1954 | Click a small, far button vs. a large, near one |
| Hick's Law | Hick and Hyman, 1952 | Find "Export" in 24 options vs. 6 |
| Jakob's Law | Jakob Nielsen, 2000 | Find the cart in the footer vs. the header |
| Chunking | George A. Miller, 1956 | Type a 10-digit number, ungrouped vs. grouped |
| Von Restorff Effect | Hedwig von Restorff, 1933 | Pick a plan when all look alike vs. one stands out |
| Law of Proximity | Gestalt psychology | Find a field when labels float vs. sit close |
| Doherty Threshold | Doherty and Thadani, 1982 | Save with no feedback vs. instant feedback |

## Run it locally

No build step and no dependencies. Download the repo and open `index.html` in a browser.

## Design decisions

- **Feel first, read second.** Each section leads with the task, so the principle is something you experience rather than memorize.
- **Same task, two versions.** Only one variable changes between A and B, so the comparison is fair.
- **Accessible by default.** Real buttons and inputs, visible focus states, high-contrast colors, light and dark mode, and reduced-motion support. Body text uses Atkinson Hyperlegible, a typeface designed for readability.
- **Private.** Times are measured in your browser and never sent anywhere.

## Add a principle

All principles live in the `LAWS` array in `index.html`. Add an object like this:

```js
{
  id: "serial-position",
  name: "Serial Position Effect",
  origin: "Hermann Ebbinghaus, 1885",
  statement: "People best remember the first and last items in a series.",
  use: "Put the most important items at the start and end of lists and navigation.",
  task: "Describe what the person should do.",
  build(stage, variant, done) {
    // Build the UI inside `stage`.
    // variant is "a" (breaks the principle) or "b" (follows it).
    // Call done() when the person completes the task.
  }
}
```

For demos that aren't timed, use `mount(row)` instead of `build` and append your own panels to `row`.

Ideas for new principles: Serial Position Effect, Tesler's Law, Peak-End Rule, Goal-Gradient Effect, Law of Common Region, Zeigarnik Effect. Open an issue if you want to claim one.

## Further reading

For a comprehensive reference on these and many more principles, see [Laws of UX](https://lawsofux.com) by Jon Yablonski. This project is independent and focuses on hands-on demos.

## License

MIT
