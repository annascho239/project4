# Implementation Plan

> EDITING DIRECTIVE: DEVELOPER AND AGENT EDIT THIS FILE COLLABORATIVELY. THE DEVELOPER MUST REVIEW AND APPROVE ITS CONTENT.

Purpose: Track the next useful build checkpoints, verification, and consequential revisions.

## Working agreement

Developer: Keep the browser preview running, choose priorities, test results directly, and plan only the next few checkpoints.

Agent: Read the project documents and inspect the files. Keep each checkpoint small enough to run and judge. Do not expand scope or mark Developer verification complete.

Start or continue a fresh chat with:

`Read the project documents, inspect the current build, and help me complete the next unchecked checkpoint.`

## Checkpoints

Main risk: the existing pause button changes only fog and lights while JavaScript timers, bats, story effects, and future audio continue. Phase 1 therefore needs one coordinated state/timing system before visual polish.

- [x] **Approve Phase 1 scope.** Use the carousel as the one complete story; preserve but deactivate the unfinished clown and tent interactions. Developer authorized the Agent to choose the most stable Phase 1 approach on 2026-10-19.
- [x] **Coordinate ambience and pause.** Added verified CC0 ambient audio and a shared pausable scheduler; Pause/Resume now coordinates CSS/Web Animations, the audio element, Web Audio, hints, story timing, ambient generation, and scene interaction.
- [x] **Complete The Last Ride.** Added distinct correct/wrong audiovisual trigger feedback, a 7-second beginning/middle/end sequence, interaction locking, clean reset, replay, ambient-audio ducking, and a static reduced-motion presentation.
- [x] **Accessibility and responsive check.** Headless Chrome smoke tests passed for controls, 44×44 minimum targets, wrong-order feedback, keyboard replay, interaction locking, pause/resume, reduced motion, and layouts at 320×568, 375×667, and 430×932.
- [ ] **Deploy and verify.** Phase 1 commit `b69cd05` was pushed to `main`. The public GitHub Pages HTML matched local `index.html` byte-for-byte, and both browser suites passed against `https://annascho239.github.io/project4/`. Remaining: the Developer must test that URL on a physical smartphone.

Test each result before continuing, including related behavior that already works. Update priorities as evidence emerges and preserve meaningful working checkpoints in git. Before delivery, verify the deployed app against the brief and specification.

## Evidence and revisions

No peer playtest observations have been recorded yet. Automated and Agent-run checks are implementation evidence, not a substitute for the required physical-phone playtest.

### Implementation evidence — 2026-10-19

- `tests/phase1-smoke.html`: all checks passed in headless Chrome, including ambience creation, audio asset loading, three responsive layouts, target sizing, wrong-order reset, story start/end, pause freeze, interaction lock/unlock, and keyboard replay.
- `tests/phase1-reduced-motion.html`: all checks passed with Chrome forced to `prefers-reduced-motion: reduce`; recurring ambient animation stayed off and the static story completed and reset.
- A 375×667 rendered scene was visually inspected. The background composition remained legible, controls did not obscure the focal point, and the carousel effect aligned with the horses.
- The original OpenGameArt page identifies the selected ambient track as CC0. The downloaded Ogg file was recognized as stereo Vorbis audio at 44.1 kHz.
- GitHub Pages served the same SHA-1 content hash for the local and deployed `index.html` (`8770c114d6824085ef6fd13880681e2511bd1cbf`), and both deployed smoke-test pages reported `pass`.
- Remaining evidence: record the Developer's physical-phone result and any peer observations.

Keep implementation progress and verification here. Update `research.md` when evidence changes a decision and `spec.md` when intended behavior changes; link to those updates rather than duplicating them. Record consequential changes, not every small adjustment.

## Saving transcripts

When directed, save the complete conversation as `transcripts/plan-YYYY-MM-DD_HHMMSS.md` or `transcripts/build-YYYY-MM-DD_HHMMSS.md`, label messages `Developer` and `Agent`, and confirm the path.
