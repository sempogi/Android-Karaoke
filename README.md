# KaraokeHD

docs/images/karaokehd-hero.png

**KaraokeHD is an experimental offline AI-powered Android karaoke platform built with .NET MAUI.**

It combines a dedicated **KaraokeHD Player** with a separate and powerful **KaraokeHD Remote companion app**.

KaraokeHD supports traditional **MIDI/KAR karaoke** and modern **MP3-LRC karaoke**. Its built-in offline AI tools can separate an MP3 into vocal and instrumental tracks, then generate synchronized **Enhanced LRC lyrics** with progressive word-level highlighting.

The platform also provides Multi-SF2 playback, dual synthesizer engines, real-time 16-channel instrument manipulation, automatic device-based microphone calibration, near-zero-latency microphone monitoring on supported hardware, singing scores, performance recording, song-specific video backgrounds, MusicXML score display, remote media management, and protected MIDI/KAR lyric repair.

The project grew from years of experimentation with karaoke systems across VB6, PSP/TiMidity, Java phones, Symbian, Python terminal playback, portable HTML players, PHP-based karaoke servers, and modern Android development.

> KaraokeHD is developed as a laboratory project.  
> Functionality, playback reliability, and architectural validation come before cosmetic enhancement.

---

## Why Is the APK More Than 300 MB?

KaraokeHD is not an ordinary karaoke player.

The Player APK is more than 300 MB mainly because it includes two offline AI models:

- An offline vocal and instrumental splitter for MP3 songs
- An offline AI lyrics creator for generating Enhanced LRC lyrics

These tools allow an MP3 legally owned by the user to be processed into an instant karaoke song.

The normal AI workflow is:

1. Select an MP3 song.
2. Separate the original recording into vocal and instrumental tracks.
3. Analyze the isolated vocal track.
4. Generate synchronized Enhanced LRC lyrics.
5. Review or quickly edit the generated lyrics when necessary.
6. Play the instrumental track with progressive karaoke highlighting.

AI processing is performed locally on the Android device. Songs do not need to be uploaded to an online transcription or stem-separation service.

Processing speed depends on the device, song duration, thermal condition, and available storage.

---

## Screenshots

docs/images/karaokehd-features.png

Additional screenshots are stored in:

```text
docs/
`-- images/
    |-- karaokehd-hero.png
    |-- karaokehd-features.png
    |-- karaokehd-player.png
    |-- karaokehd-remote.png
    |-- karaokehd-mp3-lrc.png
    |-- karaokehd-ai-tools.png
    |-- karaokehd-multisf2.png
    |-- karaokehd-recorder.png
    |-- karaokehd-background-manager.png
    |-- karaokehd-kar-editor.png
    `-- karaokehd-musicxml.png
