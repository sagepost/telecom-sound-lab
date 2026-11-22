# Telecommunications Sound Lab

A browser-based playground for telephone, radio, and telecommunications sounds, plus text-to-speech announcements.

## Try it

Open [index.html](index.html) in a browser, or enable GitHub Pages for this repository using **Settings → Pages → Deploy from a branch → main / (root)**.

The application is a single HTML file. It loads third-party speech engines and model data over the internet as needed. Speech generation with Kokoro runs locally in your browser once its resources have loaded.

## Features

- DTMF keypad with hold-to-play and programmable dialing sequences
- North American telephone dial, ringback, busy, fast-busy, and off-hook tones
- Special Information Tones (SIT) and telephone announcements
- Radio and modem tone demonstrations, telephone multifrequency tones, and custom two-tone generation
- Text-to-speech using browser voices, eSpeak NG, and Kokoro
- Telephone audio effect, WAV export for synthesized voice, and IndexedDB speech cache
- Long Kokoro announcements segmented for synthesis and cached individually
- **Idiocracy 9-1-1** humorous announcement preset

## Known issue

Long Kokoro announcements can stall during segment generation. In the reported test, *Idiocracy 9-1-1* consistently stalled on segment 22 of 31 while the browser remained responsive. Already completed segments were reused from cache after reloading. This v5 baseline does **not** yet include timeouts, worker recovery, or segment retry/subdivision.

## Notes

- Audio and voice availability depend on your browser and device.
- Initial Kokoro usage downloads a large neural model. The page uses external CDNs and Hugging Face model hosting.
- The speech cache is local to each browser and site origin; it is not stored in the Git repository.
- Generated WAV voice exports do not currently include preceding SIT tones or the telephone filter.
- The signal demonstrations are for private experimentation; do not broadcast emergency alert signaling.

## Status

Initial source import: **v5**. The next planned update is resilient long-form Kokoro synthesis with diagnostics, cancellation, retry, and recovery.
