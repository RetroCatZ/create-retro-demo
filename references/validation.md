# Validation

## Browser demo checklist

Check only implemented features, but test the **complete run** for a new demo.

**Preimplementation gate:** Verify that `requirements.md` was saved in the demo project before feature code was written, captures decisions from the entire interaction without inventing answers, and contains the timed parts/scenes, exclusions, assumptions, open questions, and acceptance criteria. For C64, verify an explicit Early/simple (through 1990 inclusive), Late/advanced (1991–2000 inclusive), or Modern Times (from 2001, emphasizing current effects and storyboards) look-and-effect phase, plus intentional cross-phase choices, separately from hardware fidelity. Verify that the user saw a simpler running order and decided to proceed. If requirements changed during or after implementation, check that `requirements-changes.md` records each change against the preserved approved baseline, with its date, old/new decision, source/reason, affected parts/timing/files, and status; material creative changes require a user decision before implementation.

1. Fresh-session load, user-gesture start, audio denial/error, silent retry, and promised `file://` or server launch. Confirm offline packaging if promised.
   Inspect a startup matching the selected computer, model, and era. For C64, check the actual demo name in `LOAD "...",8,1`, plausible load/status text, and an appropriate start command or autostart. For Amiga, check a suitable Workbench screen and visible launch of the named demo through its icon or drawer. For other systems, check a plausible platform-specific start. Check skip/restart and that the sequence does not offset the music or scene timeline; distinguish a browser simulation from native loading.
2. Each splash option has an actual effect. Check return to settings, pause/resume, restart, mute, volume, fullscreen, keyboard, and narrow/wide layouts. Repeated starts must not duplicate audio.
3. Match scene transitions, text run-out, background-tab behavior, and audio/visual sync at start, after pause/seek, and at loop/end.
4. Match actual part names, time boundaries, scenes, and effects to the approved running order. Seek to each part while playing and paused; verify audio time, picture, scroller, Effect info, and unchanged pause state.
5. Compare all parts for near-identical backgrounds or movements. Check that large and small logos leave main effects visible and follow planned scale, position, duration, entry, and exit. After an asset change, all derivatives must visibly use the new source.
6. Inspect polished C64 pixel characters and logos at output size. For each prominent character, check a recognizable silhouette and prop, a few readable clustered color areas, and restrained highlights/animation in motion. Reject both primitive placeholder geometry and fine illustrative detail that disappears at 1×; identify multi-element browser figures honestly. Also check moving bitmap glyphs at normal and enlarged sizes, a distinct later scroller after any straight intro, complete readable greetings, stable static motifs, and thin discernible raster-bar lines. CRT treatment must not create blur, flicker, or moiré. Check the finale's separate text and genuinely different scroller through complete exit.
   For an ambitious modern C64 multipart demo, check every [scene card](modern-c64-examples.md#scene-card-for-a-modern-c64-production): hero visual, typography/composition, reveal, readable development, designed exit, music cue, fallback decision, and stated fidelity. Inspect the riskiest effect in motion at target size and cadence; do not accept one attractive still. Check adjacent parts for genuinely different spatial and motion ideas, and watch the entire run for pacing and prepared finale.
   For a thematic demo, compare the result with its [motif plan](modern-c64-examples.md#motif-text-and-music-map): verify recognizable but distinct variants, planned omissions and returns, and a final callback. Watch short text scenes at normal speed for line order and reading time. Inspect intentional black/quiet holds for accidental blank frames. With multiple tunes or a media prompt, test transitions and seek/part-jump behavior across every boundary; report capture hardware separately from verified target requirements.
7. Review module boundaries, concise useful comments, function headers with parameter descriptions, explanations of unusual code, editable scrolltext files, and the README file map. After text edits, check glyph coverage and timing.
8. Verify **Effect info** for every active effect and simultaneous combinations: technical correctness, mapping to scene IDs, open/close during playback, keyboard and narrow layout, pause/seek/loop, and offline core text. A separate live-synced view needs a fallback.
9. Check English on-screen text, scrollers, menus, and technical explanation by default; respect explicit language changes. Check selected machine, C64 look-and-effect phase or other machine's era, PAL/NTSC, fidelity limits, and claims of compatibility. For C64, compare the final picture and main effects with the phase definition in [effects and eras](epochs.md#c64-three-phase-brief); do not accept a mere era label or palette swap as a different phase.

Do not confuse “the player reports playback” with listening to the music. Report source, browser, emulator, and real-hardware testing separately and name checks that remain unperformed. Automate isolated timeline, metadata, and state logic where useful; practical audio and visual inspection remains necessary.

## Skill regression examples

| Request | Critical result |
|---|---|
| Simple early C64 intro | Straight scroller and restrained effects; no default FLI/FPP/plasma showcase. |
| Plan revised during or after coding | Preserve the approved `requirements.md`; log the decision in `requirements-changes.md` and obtain review before material creative changes. |
| Long C64 demo with several parts | Show part boundaries and seekable jumps with synchronized audio, scene, scroller, and pause state. |
| Tiny retro intro | Do NOT develop baseline Effect info and splash screen and just develop a one part demo. |
| Native C64 program or original in emulator | Use a distinct development path; never substitute a browser recreation. |
| Text-only edit to an existing demo | Preserve profile and renderer; recalculate glyph coverage and scroll duration. |

These examples guide judgment; they are not evidence of end-to-end testing. Learn from real demo reviews.
