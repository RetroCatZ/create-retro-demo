# Guided brief and running order

## Questions for a new demo

Carry forward known answers. Ask in manageable rounds and explain unfamiliar demoscene terms by what viewers will see. For C64, establish whether the requested **look and effects** are Early/simple (through 1990 inclusive), Late/advanced (1991–2000 inclusive), or Modern Times (from 2001, emphasizing the latest referenced effects and storyboards). A release year alone does not decide the target, and an explicit “Late” choice selects the 1991–2000 target.

1. **Purpose and material:** Occasion, mood, machine, C64 target phase or another machine's own era, logo, images, greetings, and other text. Offer the [three C64 phases](epochs.md#c64-three-phase-brief) in plain visual terms when the phase is unresolved.
2. **Effects:** Offer a short menu from [effects and eras](epochs.md) for the selected phase. Early C64: static/simple logo, straight scroller, sparse stars or sprites, restrained raster colors. Late C64: choose a period-appropriate subset of FLD, DYCP, border effects, multiplexed sprites, FLI, plasma, FPP-style work, or vectors, with developed scenes and transitions. Modern Times C64: offer highly composed scenes, demanding showpieces, custom typography, music-led transitions, and optional thematic continuity, with feasibility and hardware limits stated. Ask which are essential or unwanted. Distinguish main attractions from backgrounds. For each prominent character, record the intended silhouette, identifying props, color treatment, and animation restraint; use the witch calibration in `epochs.md` as a style example, not a fixed asset. For logo and recurring motifs, ask frequency, scale, role, entry/exit, placement, and duration so they do not hide effects.
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

Cover the chosen total duration without gaps. For a whole track, use its measured length. Allow for greetings to be read and each scroller to exit. Identify the distinct main effect of each part and compare near-duplicate scenes. Record every logo appearance, including small variants: screen area, entry, exit, location, and duration. For C64, show the selected overall phase and each main effect's fit with it; mark intentional cross-phase choices. Keep technique-history labels such as “transitional” separate from the three user-facing phases. State important fidelity deviations.

For an ambitious modern C64 multipart demo, also prepare one [scene card](modern-c64-examples.md#scene-card-for-a-modern-c64-production) per major scene. Record its hero visual, composition and typography, entrance/exit, music cues, text behavior, feasibility tier, cost/fallback, and acceptance check. Prototype the riskiest promised effect at target size and cadence before committing the full timeline. Distinguish the observed appearance of a reference from an unverified claim about its original technique.

If the user wants a unifying theme, prepare a [motif plan](modern-c64-examples.md#motif-text-and-music-map): its distinct visual variants, each appearance's job, parts where it is absent, and final callback. For short on-screen statements, specify the exact text, line breaks, reveal, readable hold, and exit. If using multiple tunes/subtunes or a disk-change presentation, include an explicit music/media map and seek behavior. Do not infer original machine requirements from the hardware used to capture a reference video.

Before implementation, consolidate decisions from the **whole user interaction** in the demo project's `requirements.md`: content, platform/era and fidelity, the explicit C64 look-and-effect phase if applicable, music/runtime, asset sources and appearances, text, timed parts and scenes, effects and transitions, controls, delivery, technical constraints, exclusions, assumptions, unresolved questions, and acceptance criteria. Attribute user choices accurately; distinguish them from agent proposals. The document may be detailed, but always show a simpler timed running order in conversation and offer the full file on request. Ask what to change; revise both the file and summary before the user decides whether implementation may begin. After approval, leave the baseline intact and use `requirements-changes.md` for subsequent decisions as directed by SKILL.md.

## Distinguish music choices

| Question | Options |
|---|---|
| Provenance | Supplied; newly composed; procedural; none |
| Playback | Finished audio; chip/tracker player; runtime synthesis |
| Delivery | Embedded; local companion file; viewer file picker; URL |

Do not mistake a supplied recording for a request to synthesize music. Ask only distinctions that affect the deliverable.

## Profile and conflicts

Target phase, machine, and fidelity are independent. Treat “simple, like the early days” as early; references such as *Edge of Disgrace* or *Eyes* point to modern C64 unless the user asks for a historical hybrid. If given free rein, choose a phase and state it. Ask for a precise reference year only when it affects technique or fidelity. Record machine/model, video standard, phase, fidelity, limits and deviations, music/assets/text, duration/loop, settings, delivery, and validation criteria. Only offer audience settings and profile switches that are implemented and checked. Explain specific conflicts and proposed relaxations; never silently loosen strict requirements.
