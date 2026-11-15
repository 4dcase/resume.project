# resume.project
Personal resume website — Web Development course project, BBA DBE, IIM Bangalore. Built with HTML and CSS only. Responsive, animated, no JavaScript.

Web Development course project · BBA (Digital Business & Entrepreneurship), IIM Bangalore
Built with HTML and CSS only — no JavaScript, no frameworks
Built with HTML5 · CSS3 · No JavaScript

Overview

A single-page personal resume that introduces who I am, what I'm studying, what I'm learning, my interests outside coursework, and how to reach me. Everything is contained in two files:
index.html — page structure and content, written in semantic HTML5
style.css — all visual styling, layout and animation
The site works fully without JavaScript. Interactions like the flip cards and email reveal are built with CSS only.


Sections

1. Hero

The opening screen. My name appears in uppercase with a fade-in animation over a dark gradient background. Below it sits a short introduction, two buttons linking into the page, a row of interest tags, and a one-line note.
Behind the text, three blurred colour blobs drift slowly, a rotating conic halo sits centred, light beams sweep across, and small particles float up and down. These are purely decorative (aria-hidden="true") and add depth without competing with the text.

2. About
A short, centred paragraph explaining why studying economics and digital business at the same time is useful — the numbers behind a decision and the story that makes it make sense. A closing line gives a glimpse of how I think about work. Width is capped so lines stay comfortable to read on wide screens.


3. What I bring
Six cards, each covering one thing I bring to a team or a project:
Communication — breaking ideas down clearly
Art & visual thinking — sketching, composition, noticing when a layout feels off
Economics + business — incentives, trade-offs, evidence, applied to digital products
Python for data analytics — currently building the foundation
Animal welfare volunteering — patience and coordination from NGO work
Consistency over intensity — steady practice over sprinting
Each card flips on click to reveal a longer note, and flips back on a second click. The front shows a number, title, category tag and a rotate icon; the back shows the explanation on a dark gradient.
Why flip cards instead of hover-expand? Hover doesn't exist on touch screens. A hidden checkbox toggled by a <label> means the same tap works on a phone and a click works on desktop — no JavaScript required. Cards also glow pink around the edges on hover to signal they're interactive.


5. Education
A vertical timeline with a gradient line running down the left and a marker dot for each entry:
BBA (Digital Business & Entrepreneurship) — IIM Bangalore
Economics (Hons.) — University of Delhi
Python for Data Analytics — self-directed learning
Hovering an entry shifts it slightly and makes its marker glow, drawing attention to what you're reading.

6. Hobbies
Three cards for the things I do outside coursework, each with its own small themed animation:
Music — two spectrum sliders (Jeff Buckley ↔ Skrillex, Honey Singh ↔ Lifafa) with a dot sliding back and forth, plus a twelve-bar equalizer that bounces. Hovering speeds both up.
Cinema — a film strip with perforations and a flickering glow inside the frame.
Books — six book spines of different heights that fan out on hover.
A closing line ties the section together.

7. This site
Describes the project itself — that it was built from scratch with semantic HTML and one stylesheet — followed by a checklist of techniques used and a collapsible "Design notes" panel (a native <details> element). A second card lists what I want to learn next: Python fundamentals, honest data visualisation, clearer writing, and sharper design sense through daily practice.

8. Contact
A single pink "Email me" button. Hovering (or tapping, on mobile) reveals a small card with my email address as a clickable mailto: link. Keeping it to one action avoids clutter while still giving a working way to reach me.
Footer
Copyright and a note that the site uses no JavaScript, laid out with Flexbox.
Design Decisions
Colour
A five-colour palette, used with intent rather than decoration:
Near-black #0A0E17 — hero, navigation, dark surfaces, body text
Hot pink #FF2D9B — primary actions, the things you click
Cyan #00E5F0 — secondary accent, hover states, links on dark backgrounds
Violet #7C4DFF — tertiary accent, gradients, card numbers
Silver #D3D8E0 — light surfaces, tags, muted text on dark
The rule: pink appears only on clickable elements, so the eye learns quickly where to go. Cyan and violet live in gradients and hover states. Light sections use silver-tinted backgrounds with near-black text. I checked contrast throughout so nothing sits unreadable on its background.

Typography
Manrope (weights 500–800) for headings — bold with tight letter-spacing for a modern, confident feel.
Inter (weights 400–600) for body text — highly legible at small sizes.
Both are sans-serif, which reads better on screens than serif at body size.
Body line-height is 1.65; paragraphs cap at roughly 60 characters per line for comfortable reading.
Headings scale fluidly with clamp() so they shrink gracefully on phones instead of overflowing.

Layout
Flexbox for one-dimensional arrangements: the navigation bar, footer, button rows, chip lists, the equalizer and book spines.
CSS Grid for two-dimensional layouts: the card sections use repeat(auto-fit, minmax(260px, 1fr)), so columns reflow automatically — three across on desktop, two on tablet, one on mobile — without extra breakpoints.
Content is wrapped in a .container capped at 1120px and centred, so text never stretches uncomfortably wide on large monitors.

Interaction (no JavaScript)
Every interaction is pure CSS:
Flip cards — a visually-hidden <input type="checkbox"> paired with a <label>. Checking it rotates the inner face 180° via transform: rotateY() with transform-style: preserve-3d and backface-visibility: hidden. Works on click and tap alike.
Email reveal — same checkbox pattern; the address card fades and slides in on hover or when toggled.
Hover states — buttons lift and shine, cards glow pink, nav links grow an underline, timeline markers pulse, hobby animations speed up.
Scroll progress — a thin bar at the very top fills as you scroll, using animation-timeline: scroll() inside an @supports block so it degrades silently on older browsers.
Scroll reveals — sections fade and rise into view using animation-timeline: view(), again feature-detected.

Responsiveness
Two breakpoints handle the shift from desktop to mobile:
960px — the project grid collapses to one column.
760px — the navigation wraps onto two rows, all card grids become single-column, buttons go full-width, flip cards get taller so their back text isn't clipped, and the hero heading scales down.
A corrupted viewport meta tag once made phones render the whole page at desktop width and shrink it — fixed by restoring width=device-width and tightening the mobile rules.

Accessibility
Skip-to-content link for keyboard users.
Visible :focus-visible outlines in cyan on every interactive element.
aria-hidden="true" on all decorative animation (auroras, particles, equalizer, film strip, spines) so screen readers ignore them.
aria-label on the navigation and icon-only controls.
A prefers-reduced-motion media query that disables animation and transition for users who request it.
Semantic landmarks throughout: <header>, <nav>, <main>, <section>, <article>, <footer>, plus ordered and definition lists where appropriate.

Motion philosophy
Animation is kept slow and subtle — long durations, gentle easing, low-opacity glows. The goal is a page that feels alive without being busy. Nothing flashes, nothing auto-plays audio, and everything respects reduced-motion preferences.
Credits
Fonts: Manrope and Inter via Google Fonts.
Icons: inline SVG (Feather-style stroke icons), no external library.
Palette: a custom five-tone scheme chosen for contrast and calm.
