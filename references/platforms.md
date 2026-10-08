# Platforms and hardware fidelity

## Three levels

| Level | Commitment | Defensible claim |
|---|---|---|
| Loosely inspired | Coherent aesthetic; disclose modern liberties | “C64-inspired browser demo” |
| Selected limits | Define and check specific picture, sound, and timing rules | “Browser demo with the documented graphics limits” |
| Strict profile | Define a specific machine, modes, and verifiable rules; disclose deviations | “Browser recreation checked against this profile,” with test scope |

No level implies binary compatibility. JavaScript art does not run on original hardware merely because pixels and colors resemble it. Never promise exact hardware emulation without a suitable tested implementation.

## Video standard versus browser refresh rate

Distinguish the **historical hardware profile** (for example C64 PAL or NTSC) from **browser output**. PAL/NTSC affects raster structure, timing, display shape, and possibly musical event rates. Monitor refresh rate does not define this profile. Research exact figures for strict fidelity; NTSC does not universally mean exactly 60 Hz.

- **Loose inspiration and selected limits:** Render adaptively through `requestAnimationFrame` where possible (commonly 60 Hz, sometimes higher or lower). Use elapsed time rather than fixed frame counts for motion, scene changes, and music synchronization. A PAL-inspired demo may display at 60 FPS or more without becoming a hardware-faithful PAL simulation.
- **Strict profile:** Simulate the selected device's actual PAL/NTSC frame and event timing independently of browser drawing. Keep logical hardware updates separate from displayed frames. A different monitor rate may repeat or skip hardware frames; disclose the limitation and do not claim perfect smoothness.
- **Explicit user requirements prevail:** Implement a specified 50 Hz, 60 Hz, original raster schedule, or display refresh target where technically possible and document deviations.

## Compact hardware profiles (starting points)

These figures describe typical **unmodified retail machines** in common modes, not every special, overscan, or interlace mode. They guide design and engineering; they are not a full conformance suite. **Palette** means available color choices; **simultaneous colors** means colors a mode can actually use at once, subject also to local assignment rules. Raster tricks, Blitter objects, and software techniques may alter visible limits without increasing the count of physical hardware sprites.

### Commodore 64 (VIC-II, SID)

| Feature | Typical hardware characteristic |
|---|---|
| CPU / RAM | MOS 6510 or later 8500; about **0.985 MHz (PAL)** or **1.023 MHz (NTSC)**; **64 KiB RAM**, not all freely available to program data at once. |
| Graphics | **320 × 200** hires bitmap: two colors per **8 × 8** pixel cell. **160 × 200** multicolor bitmap: four color values per **4 × 8** cell, including a shared background color. Both draw from the same fixed **16-color palette**; all 16 cannot be assigned arbitrarily to every pixel. |
| Sprites | **Eight hardware sprite channels** per raster line. Hires **24 × 21** pixels, one visible color plus transparency; multicolor **12 × 21** double-width pixels, up to **three visible colors** plus transparency (two colors shared across multicolor sprites). Twofold expansion is possible. **Sprite multiplexing** can reuse channels farther down the screen for, say, **32 or more sprite images per frame**, depending on height, position, and CPU time; 32 is not a fixed maximum and does not mean 32 on one raster line. |
| Sound | **SID 6581/8580**, three programmable synthesizer voices with waveforms, envelopes, and analog filter; characteristic often gritty C64 chiptune sound. Filter behavior varies across SID revisions. |

### Amiga 500 (typical OCS model)

| Feature | Typical hardware characteristic |
|---|---|
| CPU / RAM | Motorola **68000**, about **7.09 MHz (PAL)** / **7.16 MHz (NTSC)**; commonly **512 KiB Chip RAM** stock, often upgraded to **1 MiB**. |
| Graphics | OCS: common non-interlaced PAL modes **320 × 256** with up to **32 simultaneous colors**, or **640 × 256** with up to **16**; NTSC commonly **320/640 × 200**. **4096-color palette** (12-bit). Special modes such as **HAM** and **Extra Half-Brite** extend color display under special rules, not as freely chosen per-pixel colors. |
| Sprites / graphics hardware | **Eight hardware sprite channels**, normally **16 pixels wide** with variable height, each up to **three visible colors** plus transparency; pairs may combine for more colors. The **Copper** and **Blitter** support raster control and fast graphics. Channel reuse and Blitter objects allow many more moving objects than eight, but not unlimited independent hardware sprites on one raster line. |
| Sound | **Paula**, four hardware-assisted **8-bit PCM channels** assigned to stereo sides (two left/two right); characteristic sampled instruments and tracker/MOD music rather than SID-style synthesis. |

### Amiga 1200 (AGA)

| Feature | Typical hardware characteristic |
|---|---|
| CPU / RAM | Motorola **68EC020**, about **14.2 MHz**; **2 MiB Chip RAM** stock, often later supplemented by Fast RAM. |
| Graphics | **AGA chipset**; common PAL modes **320 × 256** and **640 × 256**, NTSC commonly **200 lines**, with additional and interlaced modes. Up to **256 independently selected simultaneous colors** from a **24-bit palette (16.7 million)** in indexed modes; **HAM8** offers many more visible shades subject to pixel-color formation rules. |
| Sprites / graphics hardware | Still **eight hardware sprite channels**, not 256 independently moving hardware sprites. AGA extends color and resolution options, among other features. **Copper**, **Blitter**, and software-drawn objects support complex demos. |
| Sound | Still **Paula** with **four 8-bit PCM stereo channels**; A1200 has **no new native multichannel sound chip** over A500. Software and CPU primarily enable greater musical complexity. |

### Applying profiles

- Treat these values as a **default frame of reference** for loosely inspired work and a **starting point** for selected limits, not automatic hard validation rules.
- For explicitly requested fidelity, ask about PAL/NTSC, model revision, RAM expansions, and special modes, or record justified assumptions.
- Distinguish hardware sprites, sprites reused on other raster lines, and CPU/Blitter-drawn objects.
- For strict profiles, verify color assignment, real screen modes, raster cycles, RAM budget, and audio characteristics against relevant original documentation. Browser graphics alone never prove executability on original hardware.

### Sources and further reading

- Commodore, *C64 Programmer’s Reference Guide*, especially graphics and sound: https://commodore.ca/manuals/c64_programmers_reference/c64-programmers_reference.htm
- Commodore, *Amiga Hardware Reference Manual* (OCS/ECS; registers, sprites, Blitter, Copper, audio): https://www.amigadev.elowar.com/read/ADCD_2.1/Hardware_Manual_guide/node0000.html
- [Amiga 500 stock configuration and PAL/NTSC overview](https://www.esocop.org/model.php?id=4)
- [Amiga 1200 CPU and stock RAM](https://amiga.resource.cx/mod/a1200.html)
- [AGA specification transcript](https://github.com/rkrajnc/minimig-mist/blob/master/doc/amiga/aga/RandyAGA.txt)

## Other computers and hybrids

Describe other reference machines with the same profile fields. Research their own characteristics instead of transplanting C64 or Amiga rules. Treat intentional hybrids as a distinct design direction and name their influences.

## Demo picture versus controls

Design the modern browser controls independently of the period-inspired demo image and make the boundary clear. Under strict picture fidelity, modern logos, labels, smoothing, or effects must not silently enter the verified image area.
