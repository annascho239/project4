# Technical Specification

> EDITING DIRECTIVE: DEVELOPER AND AGENT EDIT THIS FILE COLLABORATIVELY. THE DEVELOPER MUST REVIEW AND APPROVE ITS CONTENT.

Purpose: Keep a concise, testable description of the experience currently being built.

## Working agreement

Developer: Begin with the running prototype, approve the intended behavior, test it directly, and update this file when the intended result changes.

Agent: Read `AGENTS.md`, `brief.md`, `research.md`, and this file, then inspect the project. Turn decisions into acceptance checks without inventing product choices or freezing details that still require testing.

Start a fresh chat with:

`Read the project documents, inspect the running prototype, and help me specify the next useful build checkpoint.`

## Current build contract

### Phase 1 goal

Deliver a stable smartphone playtest of an abandoned carnival that rewards exploration with one complete spooky story. The scene should feel ominous but playful and remain suitable for ages 10 and older.

### Experience and content

- The app is one non-scrolling portrait scene using `assets/halloweenbackground.png`.
- The tent is the focal point. The carousel, clown booth, and game stalls provide three distinct environmental features.
- Fog, bats, and unevenly flickering string lights create the ambient motion.
- `assets/void-estate.ogg` loops quietly after Enter. Its verified CC0 source is recorded in `research.md` and in the in-app credits.
- Text hints are contextual rather than random: discovery hints become more explicit over time, correct taps describe the next horse reacting, and a wrong tap explains that the tune broke and the sequence reset. Interaction postpones the next timed hint so messages do not compete.
- The Phase 1 story is **The Last Ride**. The User taps the three carousel horses from left to right. Correct taps glow and play rising notes; a wrong tap gives red visual feedback, a low tone, and resets progress.
- Completing the sequence begins a 7-second audiovisual story: the carousel activates, ghost riders emerge, the line “They never left” reveals the ending, and a final flash returns the scene to idle.
- The clown and tent remain environmental features. Their experimental story code and assets are preserved but their hotspots are inactive until Phase 2.

### Shared behavior

- Enter starts ambience, audio, hints, and interaction from a User gesture. It cannot initialize twice.
- While the story plays, other scene interactions are unavailable. The pause control remains available.
- Pause freezes CSS/Web Animations, audio, scheduled effects, hint timing, and scene interaction. Resume continues from the same point.
- The story can be replayed without reloading.
- Reduced-motion preference is detected before Enter. Ambient motion is omitted and the story uses static audiovisual state changes and text instead of moving effects.
- Audio playback failure must not prevent visual interaction; the live status announces the failure.

### Accessibility and layout

- The scene fills a phone viewport without scrolling and remains centered at a maximum width of 430px on larger screens.
- The background, ambience, story effects, and hotspots share one 941:1672 scene coordinate layer. That layer uses a centered-cover calculation so cropping cannot move illustrated objects away from their interactions on tall phones.
- Interactive controls and horse targets are at least 44 by 44 CSS pixels at supported phone widths.
- Enter, Pause/Resume, credits, and carousel horses work with touch/click and keyboard.
- Focus indicators, readable high-contrast text, descriptive accessible names, and live status updates are present.

### Phase 1 acceptance checks

1. Enter starts the scene once; ambient audio and all three visual ambient systems begin when reduced motion is not requested.
2. Each correct and incorrect horse tap gives distinct visual and audio feedback and communicates progress.
3. The carousel story has a clear beginning, middle, and end, lasts 5–10 seconds, locks other story interaction, resets cleanly, and replays.
4. Pause during ambience, a hint, and the story freezes the coordinated experience; Resume continues rather than restarting or skipping it.
5. The experience remains usable at 320×568, 375×667, and 430×932 CSS pixels and with keyboard-only input.
6. With reduced motion enabled, no recurring ambient animation begins and the complete story remains understandable.
7. Credits identify the Developer and all visual/audio asset origins and licenses.
8. The committed build is served over GitHub Pages and the Developer verifies it on a physical smartphone.

## Scope and revisions

Phase 1 intentionally excludes completing the clown and tent stories. They are retained for Phase 2 rather than presented as finished playtest content. The next required evidence is automated browser verification followed by the Developer's physical-phone check.

## Saving the transcript

When directed, save the complete conversation as `transcripts/spec-YYYY-MM-DD_HHMMSS.md`, label messages `Developer` and `Agent`, and confirm the path.
