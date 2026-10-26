# Research

> EDITING DIRECTIVE: DEVELOPER AND AGENT EDIT THIS FILE COLLABORATIVELY. THE DEVELOPER MUST REVIEW AND APPROVE ITS CONTENT.

Purpose: Keep the evidence and creative decisions that currently guide the build.

## Working agreement

Developer: Run the starter first. Direct the inquiry, judge sources and options, make consequential decisions, and keep this file current.

Agent: Read `AGENTS.md`, `brief.md`, and this file, then inspect the project. Help compare possibilities, test assumptions quickly, and verify external sources without delaying the prototype for exhaustive research.

Start a fresh chat with:

`Read brief.md and research.md, inspect the running project, and help me develop the scene and three spooky stories.`

---

## Scene: Abandoned Carnival at Night

**Focal point:** Massive torn big top tent, center-background, with sickly greenish-yellow glow from inside.

**Environmental features:**
1. Rusted carousel, left foreground — horses frozen mid-gallop (Story 1 trigger object)
2. Cracked clown-face cutout booth, right side — painted grin peeling (Story 2 trigger object)
3. Row of dark carnival game booths, mid-ground — ragged prizes swaying in no wind (Story 3 / Fortune Teller trigger object)

**Ambient effects (min. 3 required):**
- Ground-level rolling fog
- String lights flickering unevenly between poles
- Bats crossing a full moon in the background
- Swaying hanging signs (consider adding; zero code cost if purely CSS)

**Audio:** Looping ambient carnival/horror track — options below.

---

## Background image

**Generator:** ChatGPT / DALL-E

**Prompt used:**
> A vertical portrait-format illustration of an abandoned, sinister carnival at night. Center background: a massive torn big top tent with a sickly greenish-yellow light glowing from inside. Left foreground: a rusted carousel with frozen, skeletal horses. Right side: a weathered wooden clown-face booth, the painted grin cracked and peeling, one eye slightly off. Mid-ground: a row of dark carnival game booths with ragged prizes swaying despite no wind. Overhead: a full moon behind drifting black clouds. Ground level: thick rolling fog. String lights strung between poles flicker unevenly. Overall palette: deep blacks, sickly greens, muted purples, and dim amber. Style: dark illustrated horror, detailed, painterly, no text, no people.

**Notes:** If result is too cartoonish, add "realistic horror illustration, not cartoonish". Generated image is AI-produced (original); no external attribution required.

**Status:** Selected and implemented as `assets/halloweenbackground.png`. The portrait image contains the approved tent focal point, carousel, clown booth, game stalls, moon, fog, and string-light composition.

---

## Stories

### Story 1 — The Carousel

**Trigger:** Tap anywhere on the carousel three times; each tap wakes the next horse from left to right.
**Sequence:**
- Horses light up individually on each carousel tap (audiovisual feedback)
- On third tap: carousel starts spinning, distorted calliope music plays
- Ghostly children appear riding the horses (CSS animation / overlay)
- Shriek SFX, then children dissolve, carousel grinds to a halt
- Total runtime: 5–8 seconds; scene returns to idle

**Phase 1 revision:** The original separate-horse ordering puzzle proved unreliable because the illustrated horses overlap. One carousel-wide target now advances three clear audiovisual progress steps without requiring precise taps.

### Story 2 — The Clown

**Trigger:** Tap anywhere on the clown booth three times; the feedback advances across the visible eye, nose, and mouth.
**Sequence:**
- First tap: the visible eye pulses red; second tap: the nose warms; third tap: the pulse spreads across the grin, with descending synthesized tones
- On third tap: the visible eye burns red and the clown's mouth darkens
- A long jointed hand reaches slowly out, pauses, retracts
- A red flash reveals that it was never a costume, then the booth resets
- Total runtime: 7 seconds

**Mobile revision:** Small painted facial features would repeat the carousel's original precision problem. One broad booth target supplies three clear progress stages while remaining dependable on a phone.

**Visual-alignment revision — 2026-10-25:** Frame inspection showed the original mouth overlay at 40% scene height while the painted grin sits around 49–60%, and tall-phone cropping can hide the second eye. The final sequence uses source-image coordinates for the visible eye, nose, and mouth. The hand's wrist is anchored inside the mouth and reaches into, rather than over, the midway.

### Story 3 — The Tent

**Trigger object:** The large ripped circus tent (center, upper portion of scene)
**Trigger:** Tap the tent three times
**Sequence:**
- Each tap: the sickly interior glow pulses and a low rumble builds
- On third tap: the tent flap tears open wider, a massive shadow figure briefly fills the entrance
- A burst of sick green light floods outward, then cuts to black
- The flap falls back, the glow dims to its original state
- Total runtime: 7.5 seconds

**Risk:** The tent is a large zone — taps anywhere on it should count, not just the flap.

---

## Audio sources

### Confirmed CC0 (no attribution required)

| Use | Title | Source | Link |
|-----|-------|---------|------|
| Ambient loop option A | Haunting Chiptune Loop [Void Estate] | OpenGameArt / Zane Little Music | https://opengameart.org/content/haunting-chiptune-loop-void-estate |
| Ambient loop option B | Creepy Ambient Loop (music box/vibraphone) | OpenGameArt / epb9000 | https://opengameart.org/node/167286 |
| Story 2 SFX | Evil Laugh 2 | OpenGameArt | https://opengameart.org/content/evil-laugh-2 |

**Phase 1 selection:** “Haunting Chiptune Loop [Void Estate]” by Zane Little Music. The original OpenGameArt item page was checked on 2026-10-19 and labels the work CC0 while offering `.wav` and `.ogg` files. The `.ogg` is stored as `assets/void-estate.ogg`. Attribution is not legally required under CC0, but the in-app credits identify the creator and source.

All trigger feedback and story stings are original tones synthesized in the browser with the Web Audio API. They add no external asset or license dependency.

### CC BY 4.0 (attribution required — usable with credit)

| Use | Title | Author | Source |
|-----|-------|--------|--------|
| Ambient / carousel | Skeleton Carnival (creepy calliope + piano) | Shane Ivers | https://freemusicarchive.org/music/shane-ivers/single/skeleton-carnival/ |

### Still needed — search freesound.org with CC0 filter

Go to freesound.org → Advanced Search → License: Creative Commons 0

| Need | Search terms |
|------|-------------|
| Calliope / music box loop (carousel story) | `calliope loop`, `music box horror`, `carousel organ` |
| Creak + whoosh (clown story) | `wood creak`, `door creak`, `whoosh dark` |
| Crystal ball hum / sting (fortune teller story) | `crystal hum`, `magic sting`, `eerie tone` |
| Bat flap / wing SFX | `bat wings`, `wing flap` |
| Crowd distant murmur (optional atmosphere) | `carnival crowd distant`, `crowd murmur` |

**Verify each Freesound file's license on its individual page before use** — the license filter helps but individual clips can have conflicting metadata.

---

## Inquiry and decisions

Record only what informs the next build decisions:

- creative alternatives for the scene, stories, and audiovisual direction, with reasons for your choices
- useful sources and references, what they support, and important limitations
- experiments that resolve uncertainty, the results, and consequential trade-offs

Investigate unfamiliar techniques or asset sources as needed. Verify usage terms and keep source links and required credits here. Distinguish evidence from assumptions; the Agent's recommendation alone is not evidence.

### Phase 1 decisions — 2026-10-19

- The carousel is the one complete Phase 1 story because three taps on the ride naturally support discovery and visible progress without precision targeting.
- The clown and tent remain visual features, but their experimental hotspots are inactive for the first playtest. Presenting unfinished extra stories would make it unclear which interaction represents the intended quality bar. Their code and assets remain available for Phase 2.
- Ambient audio uses the verified CC0 track above. Short trigger and story sounds are synthesized locally so feedback responds immediately and remains pausable through the shared audio context.
- The live target is `https://annascho239.github.io/project4/`, which was serving the last committed version when checked before this Phase 1 update.

### Final project decisions — 2026-10-25

- The Developer approved completing the clown and tent stories alongside the carousel story to satisfy the three-story rubric.
- All three triggers use broad scene regions rather than small illustrated details. The trade-off is a simpler discovery mechanic in exchange for reliable touch input on narrow and tall phones.
- Each trigger still has a unique audiovisual vocabulary: blue ascending horse notes, red descending clown pulses, and intensifying green tent hums.
- All story effects use the shared pausable scheduler and Web Audio context. No additional external audio was needed.
- Progressive hints rotate among the three locations before interaction and respond to the current trigger's progress afterward.

## Revisions

Update decisions when new evidence changes the direction, linking to playtest observations in `plan.md` rather than copying them. Keep chosen behavior and asset requirements in `spec.md`. The Developer confirms when the inquiry is sufficient to continue building; exhaustive research is not a prerequisite.

## Saving the transcript

When directed, save the complete conversation as `transcripts/research-YYYY-MM-DD_HHMMSS.md`, label messages `Developer` and `Agent`, and confirm the path.
