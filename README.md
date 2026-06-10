# Honey Site — ready-to-run Next.js project

A complete Next.js (App Router + TypeScript) project with a scroll-driven
192-frame WebP animation of your honey box (عسل الطلح البلدي).

## Run it (2 commands)
```bash
npm install
npm run dev
```
Then open http://localhost:3000 and scroll.

## What's inside
- `app/` — Next.js App Router pages (`layout.tsx`, `page.tsx`, `globals.css`)
- `components/HoneyScrollSequence.tsx` — the scroll-scrub canvas component
- `public/seq/honey/frame_0001.webp … frame_0192.webp` — your 192 frames
- `package.json` — includes the `dev` / `build` / `start` scripts that were missing before

## How it works
Scroll position maps to frame index (scroll down advances, scroll up reverses)
via GSAP ScrollTrigger `scrub`. All frames preload for smooth scrubbing.
Respects `prefers-reduced-motion` (shows a static frame).

## Tuning (in components/HoneyScrollSequence.tsx)
- `scrollHeight="300vh"` — taller = slower scrub
- `scrub: 0.5` — higher = smoother follow
- `HONEY` config = { name, pathUrl: "/seq/honey", frameCount: 192 }

## Add more products later
Pass a different sequence:
```tsx
<HoneyScrollSequence sequence= name: "Grape", pathUrl: "/seq/grape", frameCount: 240  />
```
