# Implementation Plan

> EDITING DIRECTIVE: DEVELOPER AND AGENT EDIT THIS FILE COLLABORATIVELY. THE DEVELOPER MUST REVIEW AND APPROVE ITS CONTENT.

Purpose: Track the next useful build checkpoints, verification, and consequential revisions.

## Working agreement

Developer: Keep the browser preview running, choose priorities, test results directly, and plan only the next few checkpoints.

Agent: Read the project documents and inspect the files. Keep each checkpoint small enough to run and judge. Do not expand scope or mark Developer verification complete.

Start or continue a fresh chat with:

`Read the project documents, inspect the current build, and help me complete the next unchecked checkpoint.`

## Checkpoints

Main risk: expanding the stable one-story prototype could reintroduce small touch targets and unpausable effects. The final build therefore keeps broad targets and routes every story through the existing coordinated timing and locking system.

- [x] **Approve Phase 1 scope.** Use the carousel as the one complete story; preserve but deactivate the unfinished clown and tent interactions. Developer authorized the Agent to choose the most stable Phase 1 approach on 2026-10-19.
- [x] **Coordinate ambience and pause.** Added verified CC0 ambient audio and a shared pausable scheduler; Pause/Resume now coordinates CSS/Web Animations, the audio element, Web Audio, hints, story timing, ambient generation, and scene interaction.
- [x] **Complete The Last Ride.** Added three-step audiovisual carousel feedback, a 7-second beginning/middle/end sequence, interaction locking, clean reset, replay, ambient-audio ducking, and a static reduced-motion presentation.
- [x] **Accessibility and responsive check.** Headless Chrome smoke tests passed for controls, carousel-wide target coverage, three-tap progress, keyboard replay, interaction locking, pause/resume, reduced motion, and layouts at 320×568, 375×667, 390×844, 393×852, and 430×932.
- [x] **Approve final three-story scope.** On 2026-10-25, the Developer approved completing the clown and tent stories with broad phone-friendly triggers, contextual hints, and the same quality requirements as the carousel.
- [x] **Complete all three stories.** Added distinct three-step audiovisual progress, 7–7.5 second beginning/middle/end sequences, shared interaction locking, pausable scheduling, clean reset, replay, and static reduced-motion presentation for the clown booth and tent.
- [x] **Verify the expanded build.** Updated browser suites pass for all three triggers, responsive target geometry, keyboard input, pause/resume, story cleanup, locking, replay, and reduced motion. A rendered 393×852 layout was visually inspected with the three target regions exposed.
- [ ] **Deploy and verify.** Commits `0fd0410` and `b9d633e` were pushed to `main`; GitHub Pages matches the committed app and both deployed browser suites pass. Remaining: the Developer must test all three stories at `https://annascho239.github.io/project4/` on a physical smartphone.

Test each result before continuing, including related behavior that already works. Update priorities as evidence emerges and preserve meaningful working checkpoints in git. Before delivery, verify the deployed app against the brief and specification.

## Evidence and revisions

No peer playtest observations have been recorded yet. Automated and Agent-run checks are implementation evidence, not a substitute for the required physical-phone playtest.

Developer observation on 2026-10-19: tapping visible parts of the carousel horses was unreliable because the original 44px rectangles covered only the center of each figure. Revision: divide the full carousel footprint into three adjacent, non-overlapping zones extending from the horses' heads through their legs. This preserves the ordered trigger while making the illustrated figures reliable targets.

Developer observation on 2026-10-19: fixed-time hints felt random and disconnected from horse taps. Revision: make timed hints depend on current sequence progress, show immediate narrative feedback after correct and incorrect taps, and postpone the next discovery hint after interaction.

Developer observation on 2026-10-19: the third horse remained difficult to tap on a physical phone. Root cause: the background used centered `object-fit: cover` cropping while hotspots were sized against the uncropped viewport. Revision: place the background and every scene-space layer on one image-proportioned canvas and test the visible third-horse target on tall phones.

Follow-up evidence on 2026-10-19: a Developer screenshot showed that the three horses overlap diagonally, so even correctly scaled vertical bands assigned much of the circled third horse to the center trigger. Revision: trace separate silhouette-shaped regions from the screenshot and test known visible points on each horse.

Final Phase 1 interaction decision on 2026-10-19: silhouette targets also remained unreliable on the physical phone despite passing automated geometry checks. Replace the three ambiguous targets with one carousel-wide target. Three taps wake the horses left-to-right and preserve audiovisual progress without requiring precision.

### Implementation evidence — 2026-10-19

- `tests/phase1-smoke.html`: all checks passed in headless Chrome, including ambience creation, audio asset loading, five responsive layouts, shared background/hotspot alignment, carousel-wide target coverage, three-tap progress, story start/end, pause freeze, interaction lock/unlock, and keyboard replay. The complete interaction sequence also passed at 393×852.
- `tests/phase1-reduced-motion.html`: all checks passed with Chrome forced to `prefers-reduced-motion: reduce`; recurring ambient animation stayed off and the static story completed and reset.
- A 375×667 rendered scene was visually inspected. The background composition remained legible, controls did not obscure the focal point, and the carousel effect aligned with the horses.
- The original OpenGameArt page identifies the selected ambient track as CC0. The downloaded Ogg file was recognized as stereo Vorbis audio at 44.1 kHz.
- GitHub Pages served the same SHA-1 content hash for the local and deployed `index.html` (`8770c114d6824085ef6fd13880681e2511bd1cbf`), and both deployed smoke-test pages reported `pass`.
- Remaining evidence: record the Developer's physical-phone result and any peer observations.

### Final-build evidence — 2026-10-25

- `tests/phase1-smoke.html` passed every check for three active story targets, five responsive layouts, background/target alignment, minimum target size, unique progress, keyboard input, pause/resume, credits and scene locking, clean endings, and replay.
- `tests/phase1-reduced-motion.html` passed for the carousel, clown, and tent. Recurring ambience stayed off; each story used a static presentation, locked interaction, ended cleanly, and restored the scene.
- A 393×852 render with debug target colors was inspected. The blue carousel, green tent, and red clown regions were broad, adjacent, non-overlapping, and aligned with their illustrated features.
- GitHub Pages served an `index.html` with the same SHA-1 content hash as the committed file (`a1d3e1d41337ff7acdc48c7ca1426a93b23d3a16`). Both test pages also reported `pass` when run against the public HTTPS deployment.
- Automated checks do not replace the remaining Developer verification on a physical smartphone after deployment.

Keep implementation progress and verification here. Update `research.md` when evidence changes a decision and `spec.md` when intended behavior changes; link to those updates rather than duplicating them. Record consequential changes, not every small adjustment.

## Saving transcripts

When directed, save the complete conversation as `transcripts/plan-YYYY-MM-DD_HHMMSS.md` or `transcripts/build-YYYY-MM-DD_HHMMSS.md`, label messages `Developer` and `Agent`, and confirm the path.
