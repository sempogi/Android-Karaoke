# KaraokeHD

**KaraokeHD is an experimental Android MIDI/KAR karaoke platform built with .NET MAUI.**

It combines a dedicated **Player** with a separate **Controller companion**, providing SoundFont playback, synchronized karaoke lyrics, local song catalog management, queue control, channel mixing, remote media management, and protected MIDI/KAR lyric repair.

The project grew from years of experimentation with karaoke systems across VB6, PSP/TiMidity, Java phones, Symbian, Python terminal playback, portable HTML players, PHP-based karaoke servers, and modern Android development.

> KaraokeHD is developed as a laboratory project.  
> Functionality, playback reliability, and architectural validation come before cosmetic enhancement.

---

## Download

Prebuilt KaraokeHD Player and Controller packages, test releases, and related project files are available from the official project folder:

### [Download KaraokeHD from Google Drive](https://drive.google.com/drive/folders/1uzKgq8kEgkySe327vFV9i20q6Q9_ZzFi?usp=sharing)

> Packages in the download folder may include experimental and device-testing builds. Preserve your current validated APK and source package before installing or testing a newer gate.

### Important Download Notice

KaraokeHD packages do **not** include:

- SoundFont `.sf2` audio files
- Commercial MIDI or KAR song collections
- Copyrighted karaoke lyrics
- Licensed background music
- Copyrighted photographs or videos
- Third-party media libraries

Users must provide their own legally obtained SoundFont and media files.

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

KaraokeHD uses a user-supplied SF2 SoundFont and the MeltySynth audio engine to render MIDI and KAR files directly on Android.

Playback capabilities include:

- Local MIDI/KAR loading
- Minimized and background playback
- Accurate playback-position tracking
- Pause, resume, stop, and seek
- Automatic transition to the next queued song
- Persistent foreground playback notification
- Android AudioTrack output
- 48 kHz audio rendering
- Configurable local SF2 selection

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

The underlying MIDI protocol can technically route different kinds of musical data through any channel, but the General MIDI convention provides predictable percussion playback across compatible MIDI files, synthesizers, and SoundFonts.

Experimental cross-channel melodic and percussion reassignment may be explored separately in a future mixer gate.

---

## Integrated MIDI/KAR Lyrics Editor

The Controller includes an integrated workspace for repairing MIDI/KAR lyrics without manually transferring files between devices.

The normal editor workflow is:

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

Editing or replacing a file through KaraokeHD does not alter the copyright ownership or licensing requirements of that file.

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

Users are responsible for ensuring that uploaded and displayed media may legally be used on their devices.

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

This Controller build includes:

- Integrated MIDI/KAR Lyrics Editor
- Persistent editing workspaces
- Local SoundFont playback preview
- Lyric text and marker repair
- Per-token timing adjustment
- Player song download
- Validated repaired-file saving
- Round-trip validation
- Protected upload back to the Player

---

## Building the Project

### Requirements

- Windows
- .NET SDK with the Android workload
- Android SDK
- Android ARM64 device or compatible test environment
- A user-supplied and legally obtained SF2 SoundFont

### SoundFont Requirement

KaraokeHD requires a compatible `.sf2` SoundFont for MIDI/KAR audio rendering.

**No SoundFont audio files are included, hosted, mirrored, or distributed with KaraokeHD.**

SoundFont files may contain:

- Recorded instrument samples
- Synthesized audio material
- Preset definitions
- Proprietary instrument libraries
- Other copyrighted or licensed content

To avoid unauthorized redistribution, KaraokeHD does not provide third-party SoundFont files.

Users must:

1. Obtain an SF2 SoundFont from a legitimate source.
2. Review and follow the SoundFont's license.
3. Confirm that they are permitted to use it on their device.
4. Avoid redistributing it unless its license explicitly permits redistribution.
5. Select or place the SoundFont using the Player's supported local SoundFont workflow.

KaraokeHD supports standard SF2 files containing uncompressed 16-bit PCM samples.

SF3 and other compressed SoundFont formats are not currently supported.


```

The generated APK will be copied beside the build script using the release-specific filename.

---

## Project Philosophy

KaraokeHD follows several practical development principles:

- Functionality before decoration
- Device testing before feature expansion
- Proof-of-concept validation before architectural escalation
- Protected stable rollback gates
- Local-first operation
- Dedicated remote control
- Controlled file replacement
- Preservation of existing working behavior
- New features should solve observed usage problems

The project intentionally remains experimental and evolves through gated, device-tested builds.

---

## Project History

KaraokeHD is the latest stage of a long-running personal karaoke experiment.

Earlier implementations and experiments included:

- VB6 karaoke development beginning around 2004
- PSP and TiMidity experiments
- Java phone playback
- Symbian implementations
- Python terminal karaoke under Termux
- Portable monolithic HTML karaoke
- PHP server-based karaoke
- Browser-based audio engines and lyric parsers
- Modern Android Player and Controller applications

Some earlier HTML and PHP experiments were published under aliases and project identities associated with:

- `sempogi`
- `noobdou`
- `codex45`
- `doggy`
- `axlrose`
- `spartacute`
- `spartacus`
- `kentoterror`

These names belong to the same long-running body of experimental work.

---

## Media and Copyright Disclaimer

KaraokeHD is a software player, controller, editor, and interoperability-testing project.

It does not grant users ownership of, or redistribution rights to, any third-party media opened, played, edited, uploaded, downloaded, replaced, or managed through the application.

The project does not provide or distribute:

- SoundFont or SF2 audio libraries
- MIDI or KAR song collections
- Copyrighted karaoke lyrics
- Commercial karaoke tracks
- Background music
- Copyrighted photographs or videos
- Third-party media packages

Users are solely responsible for ensuring that their MIDI, KAR, SF2, lyric, image, video, and other media files are legally obtained and used according to their applicable licenses, permissions, and local laws.

Editing, repairing, converting, downloading, uploading, or replacing a file through KaraokeHD does not change:

- Ownership of the file
- Copyright status of the file
- Licensing requirements
- Redistribution restrictions
- Attribution requirements

Project contributors are not responsible for media supplied, uploaded, modified, shared, or redistributed by individual users.

---

## Software Disclaimer

KaraokeHD is an experimental laboratory project provided for:

- Software development
- Interoperability testing
- Personal experimentation
- MIDI/KAR research
- Legitimate karaoke use

The software is provided **as is**, without warranties or guarantees regarding:

- Compatibility with every Android device
- Compatibility with every MIDI, KAR, or SF2 file
- Playback accuracy with every SoundFont
- Availability of every experimental feature
- Preservation of user-supplied files
- Suitability for commercial or production use
- Continued compatibility between experimental gates

Users should preserve backups of:

- Their current validated APK
- Source packages
- SQLite song catalogs
- MIDI and KAR files
- Editing workspaces
- Configuration files
- Channel and mixer settings
- Any media managed by the application

New gates may contain experimental changes and should be tested before replacing a validated installation.

---

## Third-Party Components

KaraokeHD may use open-source libraries and platform components.

Each third-party component remains subject to its own:

- License
- Attribution requirements
- Usage conditions
- Modification terms
- Distribution terms

Compatibility with a file format, library, engine, SoundFont, or external tool does not imply ownership, endorsement, sponsorship, or authorization to redistribute third-party content created for that format or tool.

---

## Development Status

KaraokeHD is actively developed and tested as a laboratory platform.

Features may be:

- Experimental
- Device-specific
- Revised between gates
- Protected behind rollback versions
- Promoted only after successful device validation

Always preserve a currently validated gate before installing a newer experimental build.

---

## Suggested GitHub Topics

`dotnet-maui` `android` `midi` `kar` `karaoke` `soundfont` `sf2` `meltysynth` `lyrics` `remote-control` `music-player`
