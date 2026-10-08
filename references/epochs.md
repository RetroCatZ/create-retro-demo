# Effects and eras

Sections: [selection](#selection-rules) · [C64](#c64) · [Amiga](#amiga-500-and-amiga-1200) · [presenting suggestions](#presenting-suggestions) · [sources](#sources-and-limits-of-claims)

## Selection rules

Offer two creative directions:

- **Early / simple:** Intro-like fixed composition, few layers, a straight scroller, simple logo, restrained motion, and manageable color changes. Choose roughly two or three effects. Simplicity must not mean unreliable playback.
- **Late / polished:** Composed scenes, more varied effects, complex motion, transitions, and musical synchronization. Choose demanding techniques appropriate to the actual machine; merely adding particles or modern shaders is insufficient.

**Early / transitional / late** describes suitability of a particular implementation. Transitional is useful for overlaps, not a required third user mode. An early classic may still appear in late demos. A pioneering early effect may be too elaborate for an intentionally plain early intro.

These labels and date ranges are editorial design guidance, not a universal taxonomy or verified list of first appearances. Sources support techniques and selected historical anchors, not an invention date for every row. Never infer a “world first” from archive comments. Check original productions if a specific year matters.

| Profile | Early orientation | Late orientation |
|---|---|---|
| C64 | Intro aesthetics around 1983–1986; experiments as transitional | Mature productions from about 1989/1990, including later 1990s |
| Amiga 500 / OCS | Simple intros around 1987–1989 | OCS trackmos and complex demos around 1991–1994 |
| Amiga 1200 / AGA | Early AGA period around 1992–1994 | Mature AGA productions around the mid-to-late 1990s |

An “early A1200” demo means early AGA, not an A1200 production in the 1980s. Treat modern record-setting work on old hardware as another reference era, not automatically representative of 1993.

Separate era from hardware fidelity. Browser effects reproduce appearances, not proof of historical implementation. A strict profile must respect resolution, color, memory, and runtime limits. “Late” does not silently permit AGA on A500 or Fast RAM, FPU, or an accelerator on A1200. Disclose departures in loosely inspired work.

Use NTSC by default. Many European originals target PAL; their existence does not establish NTSC compatibility. Check actual timing for strict fidelity.

## C64

Choose mostly simpler implementations for early demos; add transitional techniques deliberately.

| Effect | Fit | Selection and development |
|---|---|---|
| Straight 1×1 / 2×2 scroller | Early → late | Good intro component. In a longer late demo switch later to a sine/DYCP-style, multilayer, or perspective scroller. Repeating the same straight text line throughout resembles an early intro. [C1, C4] |
| Raster bars and color cycling | Early → late | Few bars early; denser combinations later. Compose a color table per raster line with neighboring dark, mid, and bright colors and a brighter center; do not merely repeat a wide short pattern. There is no single canonical color order. [C1, C11] |
| Starfield | Early → late | Sparse points early; depth, tunnels, and layering increase complexity. [C1] |
| Sprite sine motion / moving logo | Early → transitional | Few objects on simple paths early; identify more complex reuse explicitly. [C1, C5] |
| More than eight sprites in a frame | Transitional → late | Sprite multiplexing reuses eight hardware channels at different heights. It cannot put arbitrarily many overlapping sprites on one raster line; it is not solely a late invention. [C5] |
| Open borders | Early as pioneering trick / transitional → late | Distinguish top/bottom border opening from side borders. Honey recalls side-border sprites in early 1986. Optional for a simple early intro; later work may build elaborate border compositions. Not an ordinary unrestricted fullscreen mode. [C6] |
| FLD (Flexible Line Distance) | Transitional → late | Alters character-row spacing and displaces content below. Simple FLD can suit advanced early work; JCB describes an FLD routine connected with his 1987 VSP discovery. [C2, C7] |
| DYCP (Different Y Character Position) | Transitional → late | Individually displaces characters vertically; not every wavy text strip is authentic DYCP. [C4] |
| TechTech / line-based distortion | Transitional → late | Offsets graphics by line; larger compositions are more demanding. [C1] |
| FLI (Flexible Line Interpretation) | Late | Repeatedly fetches color information for more flexible per-line assignments; it does not extend the 16-color palette. Early FLI principles are documented around 1989, but first authorship is contested. Not a default for a plain early intro. [C3, C8] |
| Plasma | Late | Distinguish color cycling, character-set, and FLI variants. Coarse blocks can be highly optimized late effects; low resolution is not automatically early. [C1, C9] |
| FPP / stretcher, twister, wave carpet | Late | Demanding raster/display manipulation; name the actual variant and period. [C1] |
| Dot vectors, filled vectors, 3D scenes | Transitional → late | Few dots lean transitional; complex filled scenes are late. Drive-assisted computation needs its own profile disclosure. [C1] |

### Executing a late C64 demo

- **Characters and sprite art:** Draw prominent figures as deliberate pixel art with a clear silhouette and a few readable features (face, hat, clothing, highlight). Add restrained shading and perhaps a short animation cycle. Simple triangles and rectangles are placeholders for a main character; a large highly colored browser painting overshoots the C64 style. Find the middle ground for the selected era/fidelity and inspect at actual output size in motion. Historical multicolor sprites trade horizontal resolution for color (12×21 double-width pixels versus 24×21 in hires). Describe larger or more colorful browser figures as possible multi-element compositions, not a single native sprite. [C5, C10]
- **Scroller choreography:** A calm straight scroller may carry the intro. In a multipart late demo, plan visibly different motion or presentation later: sine/DYCP-style character motion, perspective, or multiple layers. Choose transitions and speed so every greeting is readable. A sine-wave browser scroller is only a visual DYCP reference unless it implements the relevant VIC-II/character-set technique. [C1, C4]
- **Stable pixel art:** Use bitmap glyphs with clear edges instead of antialiased vector text at low resolution. Drive movement by time with sufficiently fine position increments; on larger browser displays consider a separate higher-resolution text layer. Design scroller entry and exit, such as edge masks, without clipping greetings. Prerender static pixel motifs at integer dimensions instead of rescaling them at varying subpixel positions every frame. Do not gratuitously coarsen pixel art: the C64 offers 320×200 hires bitmap and 160×200 multicolor bitmap, each with its own color constraints. Disclose freely inspired browser art that exceeds per-cell color limits. CRT treatment must not harm legibility or image stability. [C12]
- **Raster bars:** Build thicker apparent bands from individually discernible raster lines; the color table creates the perceived light gradient. Check source resolution, CSS scaling, and CRT overlay so thin lines are not blurred or moiré-patterned. A reproduced color table or visible scanlines do not prove VIC-II raster timing. [C11]

Historical anchors: Honey's recollection of border experiments in 1986 [C6]; VSP&IK+ dated 30 October 1987 and JCB's own explanation of his FLD routine [C7]; Charlatan dated January 1989 with discussion of FLI principles [C8]. These show overlap, not a complete history.

Example combinations:

- **Early:** Static logo, straight scroller, few stars, simple raster bars.
- **Late:** DYCP or FPP scroller, dense sprite multiplexer, plasma, and FLI graphics in separate composed scenes. Choose only a profile-appropriate subset.

## Amiga 500 and Amiga 1200

Classify effects by implementation, not name alone. Copper, Blitter, and dual playfield are original hardware capabilities, not features that arrived only in later years. [A1, A2, A3]

| Effect | Fit | A500 / OCS and A1200 / AGA |
|---|---|---|
| Straight scroller / moving logo | Early → late | Basic to both profiles; larger fonts and elaborate combinations later. |
| 2D starfield / simple star flight | Early → late | Few points early; depth and integration later. Modern examples do not establish early dates. [A7] |
| Copper bars / raster color gradients | Early → late | Few bands early; more complex color/register changes later. The Copper waits for beam positions and writes registers. [A1] |
| Sprite sine motion | Early → transitional | Few hardware sprites on paths; elaborate reuse/combination is more demanding. Check model limits. [A2] |
| BOBs / sine BOBs / vectorballs | Simple early; transitional → late when developed | Blitter objects are drawn into the bitplanes; they are not extra hardware sprite channels. Few BOBs early, large overlapping or perspective arrays later. [A2] |
| Sine scroller / TechTech | Transitional → late | Sodan & Magician 42's TechTech is archived as a November 1987 OCS production. An early pioneering use is possible; do not label the technique exclusively late. [A4] |
| Dual playfield / parallax | Simple early; transitional → late when developed | Two independently scrollable playfields are original hardware features; complex scenery/integration came later. AGA changes possibilities and color organization, not the underlying capability. [A3] |
| Alcatraz / Kefrens bars | Transitional → late | Vertical bar patterns assembled through line operations, distinct from ordinary horizontal Copper bars. Their common names are not secure inventor attribution. [A8] |
| Dot and wireframe vectors | Transitional → late | Small simple objects lean transitional; many dots, morphs, and layering are late. |
| Filled vectors / Glenz | Late | Match A500 object/face count to its limits; assess A1200 separately. Glenz names a translucent-looking style, not arbitrary modern alpha blending. |
| Plasma / color fields | Simple transitional → late | Possible on OCS; AGA gives other color gradations. Distinguish execution cost; not AGA-only. |
| Rotozoomer / texture tunnel | Late | Promise only a bounded A500 version. AGA movetable and chunky-to-planar examples show techniques but may target faster CPUs. [A7] |
| HAM still / prerendered animation | Early for display; late for complex staging | HAM6 is OCS; HAM8 is AGA. A prerendered raytracing movie does not prove realtime 3D. Classify playback and rendering separately. [A9] |
| Textured 3D / demanding chunky effects | Late, particularly AGA | CPU, RAM, internal resolution, and conversion dominate. Add accelerators only for an explicit expanded profile; “late” does not imply 68060. [A6, A7] |

Time anchors: TechTech in 1987 [A4]; Desert Dream winning the Amiga demo category at The Gathering 1993 according to original results [A5]. Placement proves no particular effect. Zaborra's original 1996 readme specifies AGA/68020 plus Fast RAM [A6]; do not silently transfer that requirement to an unexpanded A1200.

Example combinations:

- **Early A500:** Static logo, straight scroller, simple starfield and Copper bars; perhaps a few BOBs.
- **Late A500:** BOB/vectorball scene, Glenz, bars, and a limited texture effect with composed transitions; retain OCS and the selected RAM profile.
- **Early A1200:** Simple intro structure with AGA-appropriate color; extra colors alone do not make it late.
- **Late A1200:** Composed AGA scenes with plasma, tunnel, and vectors at sizes appropriate for stock hardware, or an explicitly selected expanded profile.

## Presenting suggestions

For each suggested effect, briefly give **name – fit – chosen implementation**. Example: “FLD – transitional – one bouncing text band; historically possible before the late era.” If the user requests a late effect in an early demo, state the intentional mixture and implement it. Use the same method, with machine-specific sources, for other computers; do not transfer VIC-II or Amiga tricks unexamined.

## Sources and limits of claims

Research date: 8 October 2026. Favor author articles, original manuals, firsthand developer recollections, and original documents. Production archives supply date anchors; distinguish their metadata from technical evidence. Reopen relevant sources before new precise claims about dates, timing, or compatibility.

- **C1:** [Codebase64: Demo Programming](https://codebase64.c64.org/doku.php?id=vic:demo_programming), index of attributed effect source; establishes terms and variants, not a full chronology.
- **C2:** [HCL: FLD with sample code](https://codebase64.c64.org/doku.php?id=base:fld), operation.
- **C3:** [Codebase64: FLI](https://codebase64.c64.org/doku.php?id=base:fli), color fetch, multicolor, and limits.
- **C4:** [Pasi Ojala: Demo Corner in C= Hacking 6](https://codebase64.c64.org/doku.php?id=magazines:chacking6), original DYCP discussion; technique, not first appearance.
- **C5:** [Fungus/Nostalgia: Sprite Multiplexer](https://codebase64.net/doku.php?id=base:sprite_multiplexer), author source displaying 32 sprites.
- **C6:** [Joost “Honey” Honig interview](https://www.c64.com/interviews/honig.html), retrospective firsthand border recollection, not independent proof of first authorship.
- **C7:** [VSP&IK+ and JCB's explanation](https://csdb.dk/release/?id=6176), 1987 archive date; developer's 2011 comment on FLD/VSP discovery.
- **C8:** [Charlatan and FLI discussion](https://csdb.dk/release/?id=3193), January 1989 archive date; conflicting comments rule out a definitive “first FLI” claim.
- **C9:** [Groepaz/Hitmen: Junk Modes](https://codebase64.c64.org/doku.php?id=base:junk_modes), original article dated 26 April 1999, published in Vandalism News 43; low-resolution effect modes and plasma.
- **C10:** [C64 Programmer's Reference Guide: Sprites](https://www.devili.iki.fi/Computers/Commodore/C64/Programmers_Reference/Chapter_3/page_133.html), original-manual mirror; sprite format and multicolor resolution.
- **C11:** [Codebase64: Overlapping Raster Bars](https://codebase.c64.org/doku.php?id=base:overlapping_raster_bars), author code with a per-line color table; intentional C64 color choices, not a universal palette.
- **C12:** Original C64 Programmer's Reference Guide mirrors: [hires bitmap](https://www.devili.iki.fi/Computers/Commodore/C64/Programmers_Reference/Chapter_3/page_121.html) and [multicolor bitmap](https://www.devili.iki.fi/Computers/Commodore/C64/Programmers_Reference/Chapter_3/page_127.html); resolution and color limits.
- **A1:** [Commodore Hardware Manual: About the Copper](https://amigadev.elowar.com/read/ADCD_2.1/Hardware_Manual_guide/node0048.html), original manual mirror.
- **A2:** [Commodore Libraries Manual: Simple Hardware Sprites](https://amigadev.elowar.com/read/ADCD_2.1/Libraries_Manual_guide/node0379.html) and [Bobs](https://amigadev.elowar.com/read/ADCD_2.1/Libraries_Manual_guide/node0395.html), original distinction between Blitter objects and hardware sprites.
- **A3:** [Commodore Hardware Manual: Dual Playfield Control](https://amigadev.elowar.com/read/ADCD_2.1/Hardware_Manual_guide/node007B.html), original capability.
- **A4:** [TechTech production archive and original download](https://www.pouet.net/prod.php?which=4445), November 1987 and OCS/ECS metadata, not an inventor list.
- **A5:** [Original Amiga results from The Gathering 1993](https://files.scene.org/view/parties/1993/thegathering93/info/tg93amig.txt), Desert Dream placing.
- **A6:** [Zaborra: Under the Hammer original readme in archive](https://files.scene.org/view/parties/1996/euskal96/amiga/demo/zaboruth.lha), stated hardware requirements.
- **A7:** [Haujobb: Amiga Framework](https://www.dig-id.de/amiga/framework/), author description/code for stars, movetable texture tunnel, and C2P. Modern AGA framework, not a stock A500/A1200 performance claim or historical first.
- **A8:** [Technical discussion of Kefrens bars by hitchhikr](https://www.pouet.net/topic.php?page=3&which=7523), developer explanation; do not treat names or historical attribution as settled.
- **A9:** [Commodore Libraries Manual: Hold-And-Modify Mode](https://amigadev.elowar.com/read/ADCD_2.1/Libraries_Manual_guide/node0348.html), original HAM; check additional AGA documentation for precise HAM8 limits.
