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

**Status:** Pending — Developer to generate and select.

---

## Stories

### Story 1 — The Carousel

**Trigger:** Tap three carousel horses in a specific order (left → center → right, or another order set by a clue)
**Sequence:**
- Horses light up individually on each correct tap (audiovisual feedback)
- On third tap: carousel starts spinning, distorted calliope music plays
- Ghostly children appear riding the horses (CSS animation / overlay)
- Shriek SFX, then children dissolve, carousel grinds to a halt
- Total runtime: 5–8 seconds; scene returns to idle

**Risk:** Ordering puzzles can feel arbitrary — clue system needs to hint the order, not just the objects.

### Story 2 — The Clown

**Trigger:** Tap nose → left eye → right eye (sequence)
**Sequence:**
- Each tap: that feature briefly pulses/glows with a creak SFX
- On third tap: clown's mouth cracks open wide
- A long jointed hand reaches slowly out, pauses, retracts
- Clown face resets with a reverberating laugh SFX
- Total runtime: 5–7 seconds

**Risk:** Tap targets on a painted face need to be large enough on mobile — overlay invisible tap zones over each feature.

### Story 3 — The Tent

**Trigger object:** The large ripped circus tent (center, upper portion of scene)
**Trigger:** Tap the tent three times
**Sequence:**
- Each tap: the sickly interior glow pulses and a low rumble builds
- On third tap: the tent flap tears open wider, a massive shadow figure briefly fills the entrance
- A burst of sick green light floods outward, then cuts to black
- The flap falls back, the glow dims to its original state
- Total runtime: 6–8 seconds

**Risk:** The tent is a large zone — taps anywhere on it should count, not just the flap.

---

## Audio sources

### Confirmed CC0 (no attribution required)

| Use | Title | Source | Link |
|-----|-------|---------|------|
| Ambient loop option A | Haunting Chiptune Loop [Void Estate] | OpenGameArt / Zane Little Music | https://opengameart.org/content/haunting-chiptune-loop-void-estate |
| Ambient loop option B | Creepy Ambient Loop (music box/vibraphone) | OpenGameArt / epb9000 | https://opengameart.org/node/167286 |
| Story 2 SFX | Evil Laugh 2 | OpenGameArt | https://opengameart.org/content/evil-laugh-2 |

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

## Revisions

Update decisions when new evidence changes the direction, linking to playtest observations in `plan.md` rather than copying them. Keep chosen behavior and asset requirements in `spec.md`. The Developer confirms when the inquiry is sufficient to continue building; exhaustive research is not a prerequisite.

## Saving the transcript

When directed, save the complete conversation as `transcripts/research-YYYY-MM-DD_HHMMSS.md`, label messages `Developer` and `Agent`, and confirm the path.
