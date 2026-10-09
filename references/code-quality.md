# Code quality and effect information

These rules apply to new and existing browser retro demos. Keep tiny intros simple; use clear modules for multipart work. Explicit project requirements prevail.

## Readable, compact code (required)

- Use a clear file structure and descriptive, consistent identifiers. Separate timeline/state, audio, effects/rendering, controls, configuration, and editable content. Group related effects; one file per effect is unnecessary. A multipart demo must not become one large undocumented source file. A tiny one-scene intro may use a well-sectioned main file.
- Keep comments **useful and compact**. At the top of a substantial file, state its responsibility and public interface. Give nontrivial functions a proper header describing purpose, parameters (including units/ranges where relevant), return value, and meaningful side effects. Explain unusual coding practices, timing tricks, coordinate transforms, hardware workarounds, and non-obvious trade-offs. Do not narrate self-explanatory lines.
- Keep the entry file focused on initialization and flow. Put frequently edited scrolltexts in named content files and explain supported glyphs and loading order in the README. For a promised `file://` launch, ordered classic scripts can preserve modularity; use ES modules or `fetch()` only after verifying that launch method.
- Use named configuration values for colors, dimensions, speeds, timestamps, and hardware-profile limits. Give substantial scenes/effects understandable initialization, time-based update, drawing, and cleanup boundaries. A central transport owns global time; scenes consume it rather than inventing their own clocks.
- Record each part's distinctive main effect. Compare all parts for repeated backgrounds, characters, and effect combinations; a color or caption change alone is insufficient.
- Plan every logo appearance. Keep main effects visible and avoid automatic reuse. Vary a returning mark's scale, treatment, placement, or duration. When a source image changes, find and regenerate **all** derivatives from the new file; remove stale versions and check resolution, color reduction, and actual appearances. Implement the planned entry and exit (cut, fade, or another animation), including for small repeats.
- Give the finale its own editable scrolltext and a **clearly different** scroller in scale, path, depth, or scene interaction. Check readability, entry, and complete exit against the finale duration.
- Control repeated starts, listeners, and audio sources; missing inputs/assets must produce understandable behavior. Preserve existing interfaces where practical and check affected behavior after edits. Add dependencies or performance tricks only for a concrete need; document non-obvious assumptions.

## Document historical techniques (required)

Every demo has a keyboard-accessible **Developer info** toggle, closed by default and available during playback. For each significant effect, explain in Developer Info:

1. What viewers see or hear.
2. The original chip/hardware principle and important limit, including PAL/NTSC where relevant.
3. The actual browser technique and whether it only recreates the appearance.
4. Deliberate deviations, compromises, or historical uncertainty.
5. Verifiable sources for specific claims; never invent support.

For instance, C64 sprite multiplexing reuses eight VIC-II sprite channels farther down the frame. Drawing many browser objects is not itself VIC-II sprite multiplexing.

## Viewer-facing Effect info (required)

Every demo has a keyboard-accessible **Effect info** toggle, closed by default and available during playback. Opening it must not pause music or animation or permanently cover the main picture. Even a tiny intro needs a short technical explanation. A separate companion page can supplement the view but cannot replace in-demo access unless it follows the running scene live.

For **each significant active effect**, give its name, visual description, a short explanation of the historical trick, original hardware/limits, actual browser implementation, and deviations. Explain simultaneous effects together. Optional extensions include diagrams, pseudocode, deeper source notes, and links; links alone never replace the baseline explanation. Core text must work offline when the demo is promised offline.

Keep effect metadata alongside implementation or in one catalog. Use the **same timeline/scene IDs** as rendering, never a second clock. Pause, seek, restart, and loop must update the explanation without changing transport, audio, FPS, or effect order. Keep focus visible and text readable. Live sync to another tab is optional; if provided, test browser security and offline behavior and retain a static scene-list fallback.

An illustrative record:

```js
const effectInfo = {
  rasterbars: {
    title: "Raster bars",
    visible: "Colored horizontal lines move across the screen.",
    historical: "Timed writes change VIC-II colors at raster positions.",
    browser: "Canvas draws the lines; no raster interrupt is emulated.",
    limits: "C64 color and PAL/NTSC timing differ from this rendering."
  }
};
// Timeline scenes reference active IDs such as ["rasterbars", "scroller"].
```

## Delivery and focused checks

Provide a short README with launch path, file map, editable text, assets/audio, controls, fidelity, and where effect metadata lives. Report tests actually performed; distinguish source checks, browser viewing, emulator tests, and real hardware tests.

Check full playback, pause/resume, restart, looping, errors, and affected existing features. For Effect info, check opening/closing during playback, keyboard access, narrow layout, seek/pause/loop, and simultaneous effects. Compare at least one effect's code, visible behavior, historical explanation, and sources. Automate isolated logic where useful; inspect picture and sound in practice.
