KaraokeHD 

GitHub Description and Release Notes 

Player Gate 3.8.19P.2.3  |  Version 0.3.8.25.5  |  Build 38275 

GitHub Repository Description 

Option 1: Clear and technical 

Android .NET MAUI MIDI/KAR karaoke system with SoundFont playback, synchronized lyrics, remote control, channel mixing, local catalog management, and protected KAR editing and replacement. 

Option 2: Product-focused 

KaraokeHD is a self-contained Android MIDI/KAR karaoke platform with a dedicated Controller companion, SF2 audio, synchronized lyrics, queue control, channel mixing, and remote song repair. 

Option 3: Short GitHub About text 

Android MIDI/KAR karaoke player and remote controller with SF2 playback, synchronized lyrics, channel mixing, and KAR editing. 

Suggested GitHub Topics 

dotnet-maui  android  midi  kar  karaoke  soundfont  sf2  meltysynth  lyrics  remote-control  music-player 

Release Title 

KaraokeHD Player Gate 3.8.19P.2.3 - Dynamic SF2 Drum Kit Inventory 

Release Notes 

This gate improves manual Channel 10 drum-kit selection while preserving KaraokeHD’s simple automatic percussion behavior. The mixer now reads the active SoundFont and presents the drum presets that are genuinely available instead of limiting manual selection to a fixed three-kit list. 

What’s New 

Manual Channel 10 assignment now discovers percussion presets directly from bank 128 of the active SF2. 

Displays each detected drum kit using its actual SoundFont preset name and program number. 

Supports Standard, Room, Power, Electronic, TR-808, Jazz, Brush, Orchestra, SFX, and custom kits when they exist in the loaded SoundFont. 

Removes the previous hard-coded manual list containing only Power, Jazz, and Standard drum kits. 

Keeps the convenient DEFAULT AUTO behavior using the existing Power → Jazz → Standard availability order. 

Preserves per-song manual instrument assignments through the existing assignment pipeline. 

Preserved Behavior 

MIDI/KAR playback and lyric timing 

Queue and background playback behavior 

Channel mute, solo, and melodic instrument selection 

Seven-band master EQ and Karaoke Mode 

Remote Controller channel-state synchronization 

Protected KAR download, editing, validation, replacement, backup, and rollback 

SQLite catalog and existing Player/Controller workflows 

Technical Details 

Gate 

3.8.19P.2.3 

Display version 

0.3.8.25.5 

Android build 

38275 

Platform 

.NET MAUI / Android ARM64 

Audio engine 

MeltySynth 2.4.1 with SF2 playback 

Source package 

KaraokeHD-Player-Gate-3.8.19P.2.3-SF2-Drum-Kit-Inventory.utf8 

SHA-256 

d6e3681e30f6978326f573650616684683934fa1e412022fbc00583a3e67c4d0 

Testing Focus 

Load different SF2 files and confirm that Channel 10 lists only the drum kits actually contained in each SoundFont. 

Select several discovered kits and confirm that playback changes immediately and remains stable. 

Return to DEFAULT AUTO and confirm that the Power → Jazz → Standard fallback still operates normally. 

Verify that mute, solo, remote channel cards, lyrics, queue progression, and KAR replacement remain unaffected. 

Known Scope 

This gate keeps the established General MIDI percussion convention for Channel 10. Cross-channel melodic/percussion reassignment is not introduced in this release and may be explored separately in a future experimental mixer gate. 




