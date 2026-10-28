# MeetThrough

A responsive, clickable prototype of the client journey for a community matchmaking marketplace. Built with HTML, CSS, and JavaScript. No backend, runtime dependencies, account, or paid services required.

## Explore the prototype

From this repository, run `npm start` (requires Python 3), then open port 3000 in your local browser. Alternatively, serve this directory with any static web server.

- Browse six fictional matchmakers with neighborhood/city locations and sample faith and cultural heritage details, sort by rating or price, filter by community, and save favorites.
- Create a two-step profile, optionally upload a photo, and get location-prioritized recommendations.
- Read a matchmaker’s story, sample reviews, network details, and choose 1, 3, 5, or 10 introductions.
- Complete a simulated checkout, request a call, and approve sample profile exchanges.
- After publication, use Share to send the public link through native sharing, WhatsApp, or copy it into Slack.

All people, reviews, ratings, networks, prices, bookings, and requests are fictional. No payment or message is sent. Profile information, photos, favorites, and bookings stay in browser localStorage; recipients start with their own empty state. Clear this site's browser storage to reset. No analytics, tracking, or third-party image/font requests are used. This prototype is for feedback, not real sensitive profile data. Recommendation ordering is a deterministic location demo, not a production matching engine.

## Publish to GitHub Pages

The included `.github/workflows/pages.yml` publishes only the static application files, not tests or documentation.

1. Commit and push these files to `main` in `chandra164-booth972/meetthrough`.
2. In the repository's **Settings → Pages → Build and deployment**, select **GitHub Actions** as the source.
3. Under **Actions**, run **Publish MeetThrough to GitHub Pages**, or let the push to `main` trigger it.
4. Use the successful deployment's URL as the public prototype link. It is normally `https://chandra164-booth972.github.io/meetthrough/`, but confirm the deployment succeeds before sharing.

The app uses hash routes and relative asset paths to support GitHub Pages project hosting and deep links. All site assets are local. Publication has not been performed or verified in this development session; the GitHub API returned Forbidden. No GitHub credentials should be added to the app.

## Validation

`npm test` runs a real Chromium smoke test against an already-running server at `http://127.0.0.1:3000`. For another machine, install Playwright as a development tool (`npm install --no-save --package-lock=false playwright@1.62.1`) and ensure Chromium is installed. The test defaults to `/usr/bin/chromium`; set `CHROMIUM_PATH` to another executable. It verifies discovery, favorites, profile submission, package pricing, booking, call requests, approval, persistence, mobile overflow, and local sharing guidance. These checks passed in this environment.

The public deployment, actual payments, messaging, authentication, real consent handling, availability, and production matching are outside this prototype. A real marketplace needs backend persistence and operational rules before accepting clients.
