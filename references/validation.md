# Validation

## Browser demo checklist

Check only implemented features, but test the **complete run** for a new demo.

**Preimplementation gate:** Verify that `requirements.md` was saved in the demo project before feature code was written, captures decisions from the entire interaction without inventing answers, and contains the timed parts/scenes, exclusions, assumptions, open questions, and acceptance criteria. Verify that the user saw a simpler running order and decided to proceed. If requirements changed during or after implementation, check that `requirements-changes.md` records each change against the preserved approved baseline, with its date, old/new decision, source/reason, affected parts/timing/files, and status; material creative changes require a user decision before implementation.

1. Fresh-session load, user-gesture start, audio denial/error, silent retry, and promised `file://` or server launch. Confirm offline packaging if promised.
   Inspect a startup matching the selected computer, model, and era. For C64, check the actual demo name in `LOAD "...",8,1`, plausible load/status text, and an appropriate start command or autostart. For Amiga, check a suitable Workbench screen and visible launch of the named demo through its icon or drawer. For other systems, check a plausible platform-specific start. Check skip/restart and that the sequence does not offset the music or scene timeline; distinguish a browser simulation from native loading.
2. Each splash option has an actual effect. Check return to settings, pause/resume, restart, mute, volume, fullscreen, keyboard, and narrow/wide layouts. Repeated starts must not duplicate audio.
3. Match scene transitions, text run-out, background-tab behavior, and audio/visual sync at start, after pause/seek, and at loop/end.
4. Match actual part names, time boundaries, scenes, and effects to the approved running order. Seek to each part while playing and paused; verify audio time, picture, scroller, Effect info, and unchanged pause state.
5. Compare all parts for near-identical backgrounds or movements. Check that large and small logos leave main effects visible and follow planned scale, position, duration, entry, and exit. After an asset change, all derivatives must visibly use the new source.
6. Inspect late C64 pixel characters and logos at output size. For each prominent character, check a recognizable silhouette and prop, a few readable clustered color areas, and restrained highlights/animation in motion. Reject both primitive placeholder geometry and fine illustrative detail that disappears at 1×; identify multi-element browser figures honestly. Also check moving bitmap glyphs at normal and enlarged sizes, a distinct later scroller after any straight intro, complete readable greetings, stable static motifs, and thin discernible raster-bar lines. CRT treatment must not create blur, flicker, or moiré. Check the finale's separate text and genuinely different scroller through complete exit.
7. Review module boundaries, concise useful comments, function headers with parameter descriptions, explanations of unusual code, editable scrolltext files, and the README file map. After text edits, check glyph coverage and timing.
8. Verify **Effect info** for every active effect and simultaneous combinations: technical correctness, mapping to scene IDs, open/close during playback, keyboard and narrow layout, pause/seek/loop, and offline core text. A separate live-synced view needs a fallback.
9. Check English on-screen text, scrollers, menus, and technical explanation by default; respect explicit language changes. Check selected machine, era, PAL/NTSC, fidelity limits, and claims of compatibility.

Do not confuse “the player reports playback” with listening to the music. Report source, browser, emulator, and real-hardware testing separately and name checks that remain unperformed. Automate isolated timeline, metadata, and state logic where useful; practical audio and visual inspection remains necessary.

## Skill regression examples

| Request | Critical result |
|---|---|
| Simple early C64 intro | Straight scroller and restrained effects; no default FLI/FPP/plasma showcase. |
| Early C64 with FLD/open borders | Allow deliberate advanced early/transitional tricks; do not misdate them as exclusively late. |
| Late stock A500 or A1200 | Match OCS/AGA, CPU, and RAM actually selected; no silent accelerator or Fast RAM. |
| Early A1200 | Use early AGA period, never the 1980s. |
| Late C64 “as in 1991” | Verify precise historical timing before using modern record effects. |
| Early/Late switch | Implement two visibly different effect/scene variants, not a label or filter. |
| Party demo with MP3, logo, and greetings | Ask about effects/runtime/parts; discuss the ending separately; present an editable timed plan; do not synthesize music unasked. |
| Plan revised during or after coding | Preserve the approved `requirements.md`; log the decision in `requirements-changes.md` and obtain review before material creative changes. |
| Long six-part C64 demo | Show part boundaries and seekable jumps with synchronized audio, scene, scroller, and pause state. |
| Tiny retro intro | Still provide toggled technical baseline Effect info; default demo UI language is English. |
| Native C64 program or original in emulator | Use a distinct development path; never substitute a browser recreation. |
| Text-only edit to an existing demo | Preserve profile and renderer; recalculate glyph coverage and scroll duration. |

These examples guide judgment; they are not evidence of end-to-end testing. Learn from real demo reviews.
