# Technical Specification

> EDITING DIRECTIVE: DEVELOPER AND AGENT EDIT THIS FILE COLLABORATIVELY. THE DEVELOPER MUST REVIEW AND APPROVE ITS CONTENT.

Purpose: Keep a concise, testable description of the experience currently being built.

## Working agreement

Developer: Begin with the running prototype, approve the intended behavior, test it directly, and update this file when the intended result changes.

Agent: Read `AGENTS.md`, `brief.md`, `research.md`, and this file, then inspect the project. Turn decisions into acceptance checks without inventing product choices or freezing details that still require testing.

Start a fresh chat with:

`Read the project documents, inspect the running prototype, and help me specify the next useful build checkpoint.`

## Current build contract

### Final project goal

Deliver a stable smartphone experience of an abandoned carnival with three discoverable audiovisual stories. The scene should feel ominous but playful and remain suitable for ages 10 and older.

### Experience and content

- The app is one non-scrolling portrait scene using `assets/halloweenbackground.png`.
- The tent is the focal point. The carousel, clown booth, and game stalls provide three distinct environmental features.
- Fog, bats, and unevenly flickering string lights create the ambient motion.
- `assets/void-estate.ogg` loops quietly after Enter. Its verified CC0 source is recorded in `research.md` and in the in-app credits.
- A two-part opening establishes that the carnival emptied after its final show and identifies the three attractions that still hold memories. It gives a first-time visitor enough context without revealing the interaction solution.
- Text hints rotate among all three story areas, become more explicit over time, and switch to progress-specific language after interaction. Interaction postpones the next discovery hint so messages do not compete.
- **The Last Ride:** three carousel taps wake the horses left to right with blue glows, rising notes, and connected narrative responses. The third tap begins a 7-second story in which the carousel activates, the unattended organ plays, ghost riders emerge, “They never left” reveals the ending, and a short epilogue returns the scene to idle.
- **The Painted Grin:** three clown-booth taps wake the visible eye, nose, and grin with aligned red pulses, descending tones, and connected narrative responses. The third tap begins a 7-second story in which thin rings flare around the painted pupils, a hand reaches from the unaltered grin, the text explains what is reaching back, and a short epilogue resets the booth.
- **The Last Show:** three tent taps intensify a green glow, rising hum, and description of the growing shape inside. The third tap begins a 7.5-second story in which the opening glows, a towering figure rises, the audience is revealed, and a short epilogue returns the tent to idle.
- After all three stories have been discovered, one connected ending explains that the entire carnival has finally fallen silent while keeping every story replayable.

### Shared behavior

- Enter starts ambience, audio, hints, and interaction from a User gesture. It cannot initialize twice.
- While any story plays, all story targets and the credits control are unavailable. The pause control remains available.
- Pause freezes CSS/Web Animations, audio, scheduled effects, hint timing, and scene interaction. Resume continues from the same point.
- Every story can be replayed without reloading.
- Reduced-motion preference is detected before Enter. Ambient motion is omitted and each story uses static audiovisual state changes and text instead of moving effects.
- Audio playback failure must not prevent visual interaction; the live status announces the failure.

### Accessibility and layout

- The scene fills a phone viewport without scrolling and remains centered at a maximum width of 430px on larger screens.
- The background, ambience, story effects, and hotspots share one 941:1672 scene coordinate layer. That layer uses a centered-cover calculation so cropping cannot move illustrated objects away from their interactions on tall phones.
- Interactive controls and all three story targets are at least 44 by 44 CSS pixels at supported phone widths.
- Three broad, adjacent scene regions cover the visible carousel, tent, and clown booth without overlapping each other. This favors reliable phone input over small illustrated feature targets.
- Enter, Pause/Resume, credits, and all three story targets work with touch/click and keyboard.
- Focus indicators, readable high-contrast text, descriptive accessible names, and live status updates are present.

### Acceptance checks

1. Enter starts the scene once; ambient audio and all three visual ambient systems begin when reduced motion is not requested.
2. Every carousel, clown, and tent interaction gives distinct visual and audio feedback, advances exactly one step, and communicates progress toward three taps.
3. All three stories use interaction responses, a beginning title, a middle caption, an ending caption, and an epilogue to remain understandable to a first-time visitor; each lasts 5–10 seconds, locks other interaction, resets cleanly, and replays.
4. Pause during ambience, a hint, and each story freezes the coordinated experience; Resume continues rather than restarting or skipping it.
5. The experience remains usable at 320×568, 375×667, and 430×932 CSS pixels and with keyboard-only input.
6. With reduced motion enabled, no recurring ambient animation begins and all three stories remain understandable.
7. Credits identify the Developer and all visual/audio asset origins and licenses.
8. The committed build is served over GitHub Pages and the Developer verifies it on a physical smartphone.

## Scope and revisions

On 2026-10-25, the Developer approved expanding the earlier one-story Phase 1 prototype into the complete three-story project. The existing carousel interaction remains broad because precise horse silhouettes failed physical-phone testing. The clown and tent use similarly broad, non-overlapping targets for consistency and reliability. Final acceptance requires automated browser verification followed by the Developer's physical-phone check of the deployed build.

## Saving the transcript

When directed, save the complete conversation as `transcripts/spec-YYYY-MM-DD_HHMMSS.md`, label messages `Developer` and `Agent`, and confirm the path.
