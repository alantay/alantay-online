# Site visual design (draft)

Status: draft from brainstorm 2026-09-29. Terms per `CONTEXT.md`.

## Read
Portfolio for recruiters (**Visitor**). Illustrated scrollytelling, restrained. Theme: rock climbing + bicycle touring. Must never block scanning. Targets frontend/design and full-stack roles.

Dials: VARIANCE 8, MOTION 7, DENSITY 3.

## Concept: Route Profile + 3D touring diorama hero
- **Structure (A):** an SVG elevation line is the page spine. Draws on scroll, rider dot follows. Sections are waypoints. Stays 2D.
- **Hero (3D, chosen 2026-09-30):** three.js low-poly floating island. Snow-capped peaks, lake, winding dirt road, pines, clouds. Loaded touring cyclist (rust bike = accent, tan panniers) rides the road as the visitor scrolls. Sticky split hero: copy left, scene right. Prototype: `docs/superpowers/prototypes/touring-diorama.html` (artifact https://claude.ai/artifact/PMxjmBzkgBGCiRSNs6M6h4).
- 3D in hero, Experience and Work (2026-10-02, prototype `prototype/index.html`). All three share one clay look + light rig. Never mix with flat SVG illustration.
- Superseded: layered 2D parallax crag hero (B-lite).
- Rejected: full playful "field guide" (C), reads unserious to backend recruiters.

## Sections
| Section | Treatment |
|---|---|
| Hero | 3D diorama (sticky, scroll rides bike), name, one-line role, 1 CTA, route readout (km / climb / grade) |
| Experience | Sticky 3D sport crag: one bolt per role, anchor = "Your team?". Climber clips a draw per role on scroll; belayer + rope. Stepper + height/draws readout |
| Projects | Sticky first-person ride: bars + bar bag in frame, dirt road through the clay valley, one roadside sign per project (name, grade, host). Scroll pedals to each sign; project details + link swap in on the left |
| Resume | Link only. Page + PDF stay plain (ADR 0001) |
| 404 | "Off route" |

## Tokens (proposed, confirm)
- Type: Geist (display + body), Geist Mono for labels/numbers. No serif.
- Light: bg stone `#eceeea`, ink `#131c17`. Dark: bg `#0e1411`, text `#e6e9e4`.
- One accent: rust `#c04a18` (darkened from #d0501c for white-text AA on buttons; line in dark mode `#e0652f`).
- Shape: sharp corners (radius 0), hairline rules. No cards unless elevation matters.
- Both light and dark, follow `prefers-color-scheme`.

## Motion
- Elevation line draw + rider dot: `useScroll` / `useTransform`, no scroll listeners. Motivation: shows progress, links sections.
- Hero 3D: scroll progress drives rider along road (eased), wheels/cranks turn only with distance, island rotates ~0.7 rad over hero. Pointer tilt ±few deg. Idle: island float + cloud drift only.
- Reveal on scroll via `whileInView`.
- `prefers-reduced-motion`: line fully drawn; 3D no float/drift, rider snaps to scroll position.

## 3D performance
- three.js (or react-three-fiber) in a client leaf, dynamically imported after first paint. Poster image shown until ready and as no-WebGL fallback.
- DPR cap 2, render loop paused offscreen.
- Mobile: lighter scene (fewer trees, no shadows) or poster only; decide after perf test.

## Mobile
Elevation line moves to left gutter, single column. Hero stacks: copy then scene.

## Assets needed
Poster still of the diorama (light + dark) for fallback/LCP. 3D scene is procedural; no model files.

## Open
- r3f vs plain three.js.
- Content for Projects (count, grades naming).
- Next: writing-plans.
