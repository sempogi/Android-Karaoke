# KaraokeHD

**KaraokeHD is an experimental Android MIDI/KAR karaoke platform built with .NET MAUI.**

It combines a dedicated **Player** with a separate **Controller companion**, providing SoundFont playback, synchronized karaoke lyrics, local song catalog management, queue control, channel mixing, remote media management, and protected MIDI/KAR lyric repair.

The project grew from years of experimentation with karaoke systems across VB6, PSP/TiMidity, Java phones, Symbian, Python terminal playback, portable HTML players, PHP-based karaoke servers, and modern Android development.

> KaraokeHD is developed as a laboratory project.  
> Functionality, playback reliability, and architectural validation come before cosmetic enhancement.

---

## Main Components

### KaraokeHD Player

The Player is the main Android karaoke engine.

It handles:

- MIDI and KAR playback
- SoundFont-based audio rendering
- Synchronized karaoke lyrics
- Word-level lyric highlighting
- Song queue management
- Automatic queue progression
- Local SQLite song catalog
- Background images and decorative video
- Channel mute, solo, and instrument control
- Seven-band master equalizer
- Karaoke guide-channel detection
- Remote commands from the Controller
- Protected song upload and replacement
- Camera and photo backgrounds
- Idle song-list presentation

### KaraokeHD Controller

The Controller is the dedicated remote companion and the primary control surface for KaraokeHD.

It provides:

- Automatic Player discovery
- Manual Player address configuration
- Local catalog synchronization
- Fast SQLite-backed song search
- Numeric song selection
- Remote play, pause, stop, and queue control
- Queue clearing and Auto Queue control
- Remote channel cards
- Channel mute controls
- Lyric-color selection
- Background dimmer control
- Photo upload
- Camera background streaming
- MIDI/KAR upload
- Integrated MIDI/KAR Lyrics Editor

---

## Core Features

### MIDI/KAR Playback

KaraokeHD uses an SF2 SoundFont and the MeltySynth audio engine to render MIDI and KAR files directly on Android.

Playback capabilities include:

- Local MIDI/KAR loading
- Minimized and background playback
- Accurate playback position tracking
- Pause, resume, stop, and seek
- Automatic transition to the next queued song
- Persistent foreground playback notification
- Android AudioTrack output
- 48 kHz audio rendering
- Configurable SF2 selection

---

### Synchronized Karaoke Lyrics

The Player reads lyric and text events embedded in MIDI/KAR files.

Supported presentation behavior includes:

- Uppercase lyric display
- Progressive word highlighting
- Line and screen-break markers
- Instrumental and interlude banners
- Countdown before the first lyric
- Configurable lyric fill colors
- Remote lyric-color control
- Guide-channel detection and mute support

---

### SoundFont Channel Mixer

KaraokeHD includes a Channel Strip Mixer for inspecting and controlling active MIDI channels.

Each channel can display:

- Channel number
- Detected instrument
- Manual instrument assignment
- Guide-channel confidence
- Mute state
- Solo state
- Percussion state

Mixer functions include:

- Persistent channel mute
- Channel solo
- Manual melodic instrument assignment
- Per-song instrument overrides
- Karaoke Mode
- Seven-band master EQ
- Remote channel-state reporting

---

## Dynamic SF2 Drum Kit Inventory

Starting with **Player Gate 3.8.19P.2.3**, manual Channel 10 selection is no longer limited to a hard-coded list of three drum kits.

The Player now inspects the active SoundFont and lists the percussion presets actually available in **SF2 bank 128**.

Depending on the loaded SoundFont, the available list may include:

- Standard Drum Kit
- Room Drum Kit
- Power Drum Kit
- Electronic Drum Kit
- TR-808 Drum Kit
- Jazz Drum Kit
- Brush Drum Kit
- Orchestra Drum Kit
- SFX Drum Kit
- Custom SoundFont drum kits

Each detected kit is displayed using its actual preset name and program number.

### Automatic Drum Selection

For simple operation, KaraokeHD retains its automatic fallback order:

1. Power Drum Kit
2. Jazz Drum Kit
3. Standard Drum Kit

The automatic mode is intended for convenient karaoke playback, while manual mode exposes the complete drum-kit inventory of the active SoundFont.

### General MIDI Compatibility

KaraokeHD follows the established General MIDI convention that uses Channel 10 for percussion.

The underlying MIDI protocol can technically route many types of musical data through any channel, but the General MIDI convention provides predictable playback across compatible MIDI files, synthesizers, and SoundFonts.

Experimental cross-channel melodic and percussion reassignment may be explored separately in a future mixer gate.

---

## Integrated MIDI/KAR Lyrics Editor

The Controller includes an integrated workspace for repairing MIDI/KAR lyrics without manually transferring files between devices.

The workflow is:

1. Search for a song in the Controller catalog.
2. Open the song in the KAR Editor.
3. Download the authoritative MIDI/KAR file from the Player.
4. Preserve its song code, filename, and Player information.
5. Edit lyric text and karaoke markers.
6. Adjust individual lyric-event timing.
7. Preview the edited file locally.
8. Save and reparse the repaired file.
9. Perform round-trip validation.
10. Upload the validated replacement to the Player.

Editor capabilities include:

- MIDI/KAR lyric extraction
- Token-based lyric workspace
- Text repair
- Line-break and screen-break markers
- Per-token timing offsets
- Local SF2 playback preview
- Seek and resume-from-token controls
- Current and next lyric preview
- Persistent editing workspaces
- Delayed upload support
- Round-trip validation
- Protected Player replacement

---

## Protected KAR Replacement

KaraokeHD does not directly overwrite a Player song without validation.

The replacement process verifies:

- Six-digit catalog code
- Expected filename
- Original catalog association
- Uploaded MIDI/KAR structure
- Staged-file readability
- Final committed-file integrity

The Player creates a backup before replacement and retains rollback protection if validation or file commitment fails.

---

## Song Catalog

KaraokeHD uses a local SQLite catalog for fast song searching and remote operation.

Catalog behavior includes:

- Six-digit song codes
- Filename-derived title and artist display
- Cursor-paged searching
- Manual catalog synchronization
- New-song synchronization
- Full subfolder rebuild
- Catalog export
- Validated catalog import
- Immediate catalog update after supported uploads

The normal organization workflow is:

1. Analyze
2. Sync New
3. Stop and Organize
4. Restart the Player

---

## Remote Media Features

The Controller can send additional media to the Player.

Current remote media capabilities include:

- MIDI/KAR upload
- Protected MIDI/KAR replacement
- Photo upload
- Background photo management
- Camera feed as a Player background
- Rear-camera landscape operation
- Front-camera preview
- Background transition selection
- Remote dimmer control

---

## Current Player Release

### Gate 3.8.19P.2.3

**Dynamic SF2 Drum Kit Inventory**

- Display version: `0.3.8.25.5`
- Android build: `38275`
- Target: Android ARM64
- Framework: `.NET MAUI`
- Audio engine: `MeltySynth 2.4.1`

### Main Change

Manual Channel 10 assignment now reads all available percussion presets from bank 128 of the active SoundFont.

The previous fixed manual list containing only Power, Jazz, and Standard kits has been removed.

### Preserved Behavior

This gate preserves:

- MIDI/KAR playback
- Lyric parsing and timing
- Queue progression
- Background playback
- Master EQ
- Karaoke Mode
- Channel mute and solo
- Melodic instrument assignment
- Remote channel cards
- SQLite catalog behavior
- KAR editing and validation
- Protected remote replacement
- Backup and rollback protection

---

## Current Controller Release

### Gate 3.8.16N.4.1

**Integrated KAR Editor UI Fix**

- Display version: `0.3.8.20.4`
- Android build: `38214`
- Target: Android ARM64
- Framework: `.NET MAUI`

This Controller build includes the integrated MIDI/KAR Lyrics Editor, persistent workspaces, local playback preview, timing repair, Player download, validated saving, and protected upload back to the Player.

---

## Building the Project

### Requirements

- Windows
- .NET SDK with Android workload
- Android SDK
- Android ARM64 device or compatible test environment
- A valid SF2 SoundFont

