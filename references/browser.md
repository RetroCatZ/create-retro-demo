# Browser implementation

## Launch and packaging

- Choose the simplest delivery that meets the request. Promise double-click `file://` launch only after testing it; modules or fetched resources may require a server. Ordered classic `<script>` files can keep a multipart offline demo modular.
- Bundle required fonts, libraries, music, and images for offline delivery. Add external dependencies only for a clear purpose. Check current official browser APIs when behavior or format support is uncertain.
- Show the title, profile, real options, loading/errors, and a clear start button. Offer music on/off, volume, and appropriate display controls. An Early/Late toggle must change actual effect choices, density, or scenes; a filter or renamed title is insufficient.
- Use labeled keyboard-accessible controls with visible focus. Provide sensible pause/resume, restart, mute, volume, fullscreen, and return-to-settings behavior; handle unavailable fullscreen. Do not let global shortcuts intercept form fields. When music fails, offer an explicit silent start or retry.
- Store settings locally only with a fallback. Do not upload viewer files without consent.

## Audio and transport

- Start audio from a user gesture; autoplay permission cannot be assumed. Avoid duplicate players/sources after restart.
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
