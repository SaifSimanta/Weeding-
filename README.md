# Emerald Pines Country Club — Wedding Planner (Demo)

A clickable, front-end-only wedding planning demo for Emerald Pines Country Club.
All data is fictional, lives in browser memory, and resets on page refresh.
No backend, database, real payments, emails or texts.

## Demo login

Open the app and you land on `/login`. Any email and password work.
Tap a role card to auto-fill:

| Role           | Email                            | Password  |
| -------------- | -------------------------------- | --------- |
| Wedding Client | amelia.caldwell@example.com      | demo1234  |
| Coordinator    | elena.rhodes@emeraldpines.club   | demo1234  |
| Administrator  | yasmin.park@emeraldpines.club    | demo1234  |

Once signed in, the top bar lets you switch roles, open Presentation Controls
(simulated payment/refund outcomes, reset data) and sign out.

## Features

- Client: home, availability calendar with venue photo peek, wedding plan form
  (guest capacity hint), review, simulated refundable $100 deposit, request status
  with 3-day review countdown, receipts, help/inquiries
- Coordinator: dashboard, review queue, requirement review, approve/revise,
  venue closures, refunds and refund processing, help
- Administrator: dashboard, staff accounts (create, edit, deactivate), help

## Tech stack

React 19, React Router, Tailwind CSS, shadcn/ui, lucide-react, sonner, CRACO.

## Run locally

Requires Node.js 18+ and Yarn.

```bash
yarn install
yarn start        # http://localhost:3000
```

Production build:

```bash
yarn build        # outputs to /build
```

## Deploy

The `build` folder is a static site. It works on Vercel, Netlify, GitHub Pages
or any static host. Configure a single-page-app fallback so all routes serve
`index.html` (for Netlify, add `/* /index.html 200` to `public/_redirects`).

## Project structure

```
src/
  App.js              routes + login guard
  index.css           theme (emerald / ivory / gold)
  state/store.jsx     shared in-memory demo data
  components/         Logo, Shell (nav + role switcher), StatusBadge, ui/ (shadcn)
  pages/              Login, client, Coord*, Admin* screens
```
