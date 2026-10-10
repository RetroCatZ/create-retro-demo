# C64 demo music composition

Use this guide when the user requests **newly composed** music. A supplied MP3 or SID is a source to inspect or play, not permission to rewrite it. Record whether the deliverable is a native SID tune, a modern SID-inspired soundtrack, or playback of supplied music. Honor the agreed fidelity, duration, loop, and scene plan in `requirements.md`.

## Musical quality criteria

The finished track must work as music over a complete listen, including quiet passages, scene transitions, and its ending or loop. Judge outcomes, not compliance with a fixed tempo, chord progression, bar count, or voice assignment.

- **Identity and development:** Establish a memorable original motif or musical idea. Develop it through phrasing, rhythm, harmony, register, timbre, or context; avoid an unchanged short loop standing in for an arrangement.
- **Bass and pulse:** Give the bass a deliberate rhythmic and harmonic role. Make its interaction with percussion, arpeggios, and melody clear. Repeated roots are valid when they build the intended tension.
- **Melody and counterpoint:** Shape leads into phrases with breath, response, and variation. Give supporting lines room to be heard; do not use constant ornament to disguise a missing melodic idea.
- **Arpeggios:** Use them for harmonic definition, propulsion, or counterpoint. Vary density and articulation according to the phrase; leave space where the melody or effect cue needs it.
- **Timbre and mix:** Choose waveforms, envelopes, pulse-width movement, filtering, noise, and articulation intentionally. Keep bass and lead legible; remove unintended clipping, piercing sustained highs, and masking.
- **Arrangement and transitions:** Give sections distinct purposes and an audible arc. Prepare important entrances, breakdowns, returns, and the finale with musical cues, fills, harmonic movement, or contrast. Make cuts, fades, cadences, and loop joins intentional.

Creative departures are welcome when they strengthen the track. A sparse passage, unusual meter, silence, or an unexpected timbre can meet these criteria better than a conventional chiptune pattern.

## Technical path

### Native SID music

- Specify target C64 timing and SID variant when fidelity matters. Arrange for the SID's **three programmable voices**; plan voice sharing among bass, lead, harmony/arpeggio, and percussion instead of assuming extra simultaneous channels.
- Sequence note frequency, gate, waveform, pulse width, ADSR, and filter changes from a deterministic player tick. Use triangle, sawtooth, pulse, and noise within their hardware behavior; use ring modulation, hard sync, and filtering where they serve the composition.
- Provide valid initialization and play routines and the intended subtune selection. Distinguish a SID tune container from a runnable C64 demo. Verify timing, voice behavior, and playback in a suitable SID player or emulator; claim real-hardware validation only if performed. Account for 6581/8580 filter differences when the chosen sound relies on them.

### Modern SID-inspired audio

- Keep an explicit musical event sequence: notes, durations, instrument settings, automation, tempo changes, section boundaries, and cue markers. Synthesize with Web Audio against its audio clock, or render a local audio asset from the same arrangement. Do not trigger notes from `requestAnimationFrame` or visual frame counts.
- If synthesizing live, schedule ahead from one transport clock; cancel and rebuild pending events after pause, seek, restart, or loop. Prevent duplicate voices and clicks at transport changes. Start audio from a user gesture and handle decoder or device failure.
- Recreate SID-like character with purposeful oscillator shapes, envelopes, pulse modulation, noise, arpeggios, and filter movement. Additional layers, stereo, and effects are allowed when fidelity permits, but describe the result as **SID-inspired** unless an actual SID player or emulator is used.
- Bundle the audio and required player code for the promised offline mode. Provide an export or playback path that can be tested independently of the visuals.

## Music and visual timeline

Mark musical cues at meaningful events: motif entrance, fill, break, harmonic turn, return, or climax. Map scene boundaries and major effect changes to selected cues, while allowing visual counterpoint and calmer sections. Do not pulse every effect on every beat by default.

Use one authoritative transport, normally audio playback time. Derive current section, visual state, scroller, and cue from that time. Define behavior for start, pause, seek, part jump, restart, background-tab return, and loop; resynchronize after each. If audio and visual lengths differ, specify the ending or repetition rule. Store cue positions with the arrangement so edits cannot silently desynchronize the demo.

## Short acceptance check

1. Listen to the **whole** track at normal volume. Identify the hook, bass role, melodic development, arpeggio purpose, contrast, transitions, and finale; revise filler.
2. Listen to isolated voices and the full mix for masking, harshness, accidental silence, clipping, and clicks. Check the loop seam or final decay.
3. Run the demo through start, pause, seek, part jump, restart, and loop. Confirm cue and picture alignment after each action.
4. Report the actual source files, identified subtunes, playback environment, and checks performed. Keep unverified musical interpretations and unperformed hardware/listening tests explicit.
