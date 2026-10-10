# Modern C64 demo examples

Use this to calibrate the **Modern Times** C64 look-and-effect phase (from 2001 onward, emphasizing current ambitious effects and storyboards). Select the phase first with the [three-phase guide](epochs.md#c64-three-phase-brief); keep hardware fidelity and browser-versus-native delivery separate.

## Scene card for a modern C64 production

Before coding each major scene, record: its purpose and timed range; one hero visual and occupied screen area; art, palette, type, and text; exact entrance, development, and exit; musical cue; proposed rendering technique and fidelity claim; performance or native-hardware risk; a simpler coherent fallback; and what must be visible at normal playback size. Prototype the riskiest effect in motion before filling the full timeline. A still image or generic shader does not satisfy a promised moving C64-style effect.

Classify its technical path as **composed art/motion**, **algorithmic visual**, or **raster/hardware-dependent**. A browser version may reproduce appearance, but must not claim native C64 execution. A native plan for FLI, FPP, multiplexing, border work, or other raster-dependent effects needs the selected mode, color/cell limits, memory and cycle budget, and emulator or hardware verification before promising it.

## Motif, text, and music map

If a theme is wanted, list each motif appearance by part: what stays recognizable, what changes in scale/number/color/form, and whether it is a hero image, pattern, transition, text carrier, or final callback. Leave some parts free of the motif. For each short statement, specify exact wording, line breaks, glyphs, reveal order, readable hold, and exit. For multiple tunes or subtunes, record the verified source, duration, start/end, transition, and pause/seek/jump behavior. If a disk or loader prompt is requested, define whether playback waits for the viewer and how it resumes; a browser simulation is not native loading.

At final review, watch the complete run with music. Verify that adjacent parts differ in more than palette, text remains readable without pausing, deliberate quiet/black holds are not rendering gaps, motif returns feel intentional, music and picture stay aligned across every part boundary, and the finale completes its planned exit. Report video observations, hypotheses, browser results, emulator tests, and real-hardware results separately.
