# Guided brief and running order

## Questions for a new demo

Carry forward known answers. Ask in manageable rounds and explain unfamiliar demoscene terms by what viewers will see. “Late era” alone does not determine effects or pacing.

1. **Purpose and material:** Occasion, mood, machine/era, logo, images, greetings, and other text.
2. **Effects:** Offer a short menu from [effects and eras](epochs.md). For a late C64 demo, this might include raster bars, starfield, plasma, sprites, a sine/DYCP-style scroller, and pixel art. Ask which are essential or unwanted. Distinguish main attractions from backgrounds. For logo and recurring motifs, ask frequency, scale, role, entry/exit, placement, and duration so they do not hide effects.
3. **Runtime and structure:** Full track, excerpt, or fixed duration? Measure a supplied track; do not estimate duration from file size. Ask about fade/loop, number and character of **parts**, scenes within parts, and calm versus fast pacing. Offer jumps to part starts for seekable multipart browser demos.
4. **Remaining implementation choices:** Ask only unresolved questions about fidelity, splash screen, and settings. Explain defaults from SKILL.md as proposals.

The conversation language does not determine demo language. Demo text, scrollers, menus, and Effect info default to English unless explicitly changed. For vague preferences, offer two or three concrete options. 

## Ask about the final part separately

After general effects and runtime are known, ask:

- What is the climax: a new effect, returning motifs, logo, greetings/credits, or another idea? What must appear or be absent?
- What is the finale's own scrolltext, and how will its scroller differ visibly? Propose a separately editable draft if wording is unknown.
- When does it begin musically, and how long does it last? Mark unknown musical timing as provisional.
- Does it end on a held image, fade, hard cut, end card, or seamless loop?

Show the final part's scenes, duration, and intended impact explicitly; “finale with effects” is too vague.

## Running order before implementation

Present a compact table:

| Part | Start–end | Duration | Scenes/purpose | Main and supporting effects | Logo/text, entry/exit, music |
|---|---|---:|---|---|---|
| 1 · Opening | `00:00–00:30` | `0:30` | Intro | Named effects | Placement and transition |
| … | … | … | … | … | … |
| Final part | `…–end` | … | Agreed climax | Named effects | Final image/fade/loop |

Cover the chosen total duration without gaps. For a whole track, use its measured length. Allow for greetings to be read and each scroller to exit. Identify the distinct main effect of each part and compare near-duplicate scenes. Record every logo appearance, including small variants: screen area, entry, exit, location, and duration. Briefly classify effects as early, transitional, or late and state important fidelity deviations. Ask what the user wants changed and wait for feedback or approval before coding. Update times and total duration after revisions.

## Distinguish music choices

| Question | Options |
|---|---|
| Provenance | Supplied; newly composed; procedural; none |
| Playback | Finished audio; chip/tracker player; runtime synthesis |
| Delivery | Embedded; local companion file; viewer file picker; URL |

Do not mistake a supplied recording for a request to synthesize music. Ask only distinctions that affect the deliverable.

## Profile and conflicts

Era, machine, and fidelity are independent. Treat “simple, like the early days” as early; if given free rein, choose a direction and state it. Ask for a reference year only when precision matters. Record machine/model, video standard, era, fidelity, limits and deviations, music/assets/text, duration/loop, settings, delivery, and validation criteria. Only offer audience settings and profile switches that are implemented and checked. Explain specific conflicts and proposed relaxations; never silently loosen strict requirements.
