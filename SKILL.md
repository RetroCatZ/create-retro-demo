---
name: create-retro-demo
description: Create or revise browser-based retro demos inspired by early or late C64, Amiga, and other home computer productions, with demoscene effects, music, and a configurable splash screen.
---

# Retro Demo Creator

## Defaults

Honor explicit user choices. Otherwise use a browser demo, Amiga 500 for an unspecified “Amiga,” NTSC where applicable, loosely inspired fidelity, local HTML/assets, a configurable splash screen, and **English** on-screen text, scrollers, menus, and effect information. Ask the user to choose an early or late style and the music. Native output or an original binary in an emulator is a separate development path; do not substitute a browser recreation or claim native compatibility.

## Workflow

1. **Brief the user.** Carry forward existing answers. Ask in manageable groups about wanted and unwanted effects, runtime and music, assets and text, number and pace of parts, and looping. Offer era-appropriate effect choices with plain visual descriptions. For longer multipart browser demos, offer jumps to part starts when media is seekable. Keep conversation language independent of the demo's default English. Use [briefing](references/briefing.md).
2. **Plan the ending separately.** Ask what makes the final part a climax, its effects, duration, musical cue, text, logo use, and final frame/fade/loop. Give it an editable scrolltext and a scroller technique visibly different from earlier parts.
3. **Present a running order before coding.** Show each **part**, its scenes, start/end/duration, main effects, text/logo, transitions, and music cues. Cover the full runtime. Distinguish every part from the others; identify logo-free parts and keep main effects visible. Plan entry, exit, placement, and duration even for small returning graphics. Use a suitably detailed C64 pixel style and change scroller technique after a straight intro in a late multipart demo. Let the user revise the plan; wait for feedback or approval unless they expressly request immediate implementation. See [briefing](references/briefing.md) and [effects and eras](references/epochs.md).
4. **Build the demo.** Prefer straightforward HTML/CSS/JavaScript unless the project requires otherwise. Separate timeline, audio, rendering, controls, configuration, and editable scrolltexts into understandable modules for multipart work. Document code as specified in [code quality](references/code-quality.md). Provide a closed-by-default **Effect info** view with a technical baseline explanation of active effects; only extra depth and links are optional. Drive it, named part boundaries, jumps, music, visuals, and scrollers from one authoritative timeline. Synchronize start, pause, seek, restart, and loop. Let text complete its run. When a source asset changes, regenerate and check every derivative from the new source.
5. **Validate and deliver.** Compare the implementation with the agreed running order. Check playback, part jumps while playing and paused, audio/visual sync, the promised launch method, and actual appearance. Inspect scrollers and pixel art at normal and enlarged sizes for blur, jerkiness, flicker, clipping, and obscured effects. Deliver code and a concise README with launch steps, hardware profile/fidelity, asset and music provenance, and tests actually performed. See [validation](references/validation.md).

## Load details only when needed

- [Briefing](references/briefing.md): new demos, unclear music, conflicting requirements, and running orders.
- [Effects and eras](references/epochs.md): effect choice, historical fit, C64 artwork, scrollers, and raster bars.
- [Platform profiles](references/platforms.md): specific hardware limits or strict fidelity; verify precise claims in primary sources.
- [Browser implementation](references/browser.md): audio, loading, offline packaging, controls, and playback.
- [Code quality](references/code-quality.md): every implementation or code change, including mandatory effect information.
- [Validation](references/validation.md): complete demos, playback changes, or relevant checks for small edits.
