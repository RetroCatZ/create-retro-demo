# Browser implementation

## Launch and packaging

- Match the opening to the selected computer, model, and era rather than reusing one machine's startup screen for all demos. After the startup, transition to the configurable splash screen or first demo scene. Use the actual demo name where the interface shows a program or disk name. For other systems, choose a recognizable, technically plausible boot, loader, command prompt, or desktop for that platform; do not invent a universal startup command.
- For C64 demos, show a brief C64 BASIC V2-style screen before the configurable splash screen or first demo scene: blue screen and border, light-blue monospaced/PETSCII-like text, startup banner, memory line, `READY.`, and a visible cursor. Type `LOAD "DEMO NAME",8,1` with the actual demo name in place of `DEMO NAME`; then show plausible disk status (`SEARCHING FOR ...`, `LOADING`, `READY.`) and a visible start command. Use `RUN` for a BASIC program, `SYS <address>` for machine code when its entry address is known, or an accurate autostart transition for a genuine autostart loader. Do not imply that `LOAD` alone executes a normal program. In a browser recreation, this is a visual simulation, not proof that a C64 binary was loaded. Keep it short, readable, and skippable; keep its time separate from the demo/music timeline unless the approved plan specifies otherwise.
- For Amiga demos, first show a recognizable Workbench desktop consistent with the selected Amiga model and period: suitable screen styling, menu bar, pointer, and disk/drawer or program icon. Show the viewer opening the demo's disk/drawer and launching its named icon, or another Workbench action that visibly starts the demo. Avoid presenting C64 BASIC commands on an Amiga. A browser recreation simulates this interaction; do not imply that AmigaOS or a native executable is actually running. Keep the sequence short and skippable, and start the demo/music timeline at the transition unless the approved plan specifies otherwise.
- Choose the simplest delivery that meets the request. Promise double-click `file://` launch only after testing it; modules or fetched resources may require a server. Ordered classic `<script>` files can keep a multipart offline demo modular.
- Bundle required fonts, libraries, music, and images for offline delivery. Add external dependencies only for a clear purpose. Check current official browser APIs when behavior or format support is uncertain.
- Show the title, profile, real options, loading/errors, and a clear start button. Offer music on/off, volume, and appropriate display controls. For C64, offer Early / Late / Modern Times only for implemented variants; Amiga may retain Early/Late. Switching phase must change actual effect choices, density, scene development, or storyboard; a filter or renamed title is insufficient.
- Use labeled keyboard-accessible controls with visible focus. Provide sensible pause/resume, restart, mute, volume, fullscreen, and return-to-settings behavior; handle unavailable fullscreen. Do not let global shortcuts intercept form fields. When music fails, offer an explicit silent start or retry.
- Store settings locally only with a fallback. Do not upload viewer files without consent.

## Audio and transport

- Start audio from a user gesture; autoplay permission cannot be assumed. Avoid duplicate players/sources after restart.
- If the platform startup sequence delays the demo, ensure the eventual music start still satisfies browser user-gesture rules; provide a clear start control or silent fallback when necessary.
- Use supplied music as supplied, record credits, and handle load/decoder errors. A newly composed track needs an actual arrangement; do not call a placeholder tone a soundtrack. Schedule synthesis against audio time, not animation frames.
- Chip/tracker formats need a suitable verified player and shipped dependencies. Normal audio elements do not support every historical format. Handle URL/network failures without silently substituting another recording.
- Define **one authoritative clock**, normally audio playback time for music-led demos. Model loading, ready, playing, paused, and error states; prevent double starts. Keep visuals synchronized after start, pause, restart, seek, background-tab return, and loop. Define what happens when music and visual durations differ.
- Separate named part boundaries from scene changes. A jump to a part start seeks the authoritative transport and derives picture, scroller, label, and Effect info from it while preserving play/pause. Disable jumps clearly if media is not seekable.
- Calculate scroller runtime from glyph/text width, speed, viewport, and exit travel. Allow for shadows and holds. Offer speed changes only where music, events, and legibility remain coherent.

## Image and performance

- Separate internal render resolution from CSS display size and pixel aspect. Choose scaling and image smoothing deliberately.
- **Do not confuse PAL/NTSC hardware timing with browser refresh.** Use `requestAnimationFrame` by default at the actual display rate, including 90/120/144 Hz. Compute motion and events from elapsed time or the authoritative audio time, never fixed steps per browser frame. Handle long gaps after background pauses.
- For **strict fidelity**, simulate the selected PAL/NTSC hardware raster/event clock separately; browser frames only display the current logical state. Rate mismatch can repeat or skip hardware frames. Interpolate only where it does not falsify the claimed behavior.
- Bound per-frame work and memory. Check a full run and longer loops where leaks are plausible. Reduce optional rendering cost when needed without silently changing the selected hardware profile or music speed.

## Effect information

The mandatory Effect info behavior and content live in [code quality](code-quality.md). Its core explanation is local/offline when offline delivery is promised; opening the view never changes playback. Test `file://` and browser security behavior for optional separate-tab live sync, and keep a static fallback.
