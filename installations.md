KaraokeHD Initial Installation
==============================

ABOUT KARAOKEHD
---------------

KaraokeHD is a large APK of more than 300 MB because it includes two
built-in offline AI models:

- An offline vocal and instrumental splitter for MP3 songs
- An offline AI lyrics creator that generates Enhanced LRC lyrics

These AI tools allow an MP3 legally owned by the user to be turned into
an instant karaoke song. KaraokeHD can separate the original MP3 into
vocal and instrumental tracks, then generate synchronized Enhanced LRC
lyrics with progressive word-level highlighting.

All AI processing is performed directly on the device. An internet
connection is not required during processing.

KaraokeHD is more than an ordinary karaoke player. It supports:

- MIDI and KAR karaoke
- MP3 karaoke with standard LRC or Enhanced LRC lyrics
- Offline AI vocal and instrumental separation
- Offline AI-assisted Enhanced LRC creation
- Progressive word-level lyric highlighting
- Song queue and playlist management
- Multi-SF2 SoundFont-based MIDI playback
- Dual synthesizer engines
- Real-time 16-channel instrument manipulation
- Background images and videos
- Background Video Manager with song-specific video assignments
- Microphone monitoring and automatic device-based calibration
- Singing scores and performance recording
- Instrument-only and instrument-plus-vocal recording
- Advanced audio, lyrics, background, and performance controls


MULTI-SF2 AND DUAL SYNTH ENGINES
--------------------------------

KaraokeHD is not limited to a single SoundFont. It can load and manage
multiple SF2 files as one searchable instrument catalog.

During MIDI or KAR playback, KaraokeHD can search across the available
SF2 catalog and select the most suitable SoundFont, bank, program, and
instrument for each MIDI channel.

Its 16-channel MIDI controls allow real-time manipulation, including:

- Assigning a different SF2, bank, program, and instrument to each channel
- Reassigning instruments while the song is playing
- Moving a MIDI channel from one SoundFont to another
- Muting, soloing, and monitoring individual channels
- Saving manual instrument selections for later playback

One song may therefore use instruments taken from several SoundFonts,
with KaraokeHD controlling the complete 16-channel arrangement.

KaraokeHD includes two synthesizer engines:

MeltySynth
    The carefully tuned KaraokeHD engine. Special handling is applied to
    guitar instruments, including bends and expressive playback, to make
    MIDI guitars sound more natural and closer to a real guitar
    performance.

FluidSynth
    The convenient alternative engine for users who prefer an easier
    route to rich and polished playback. It provides broad SoundFont
    compatibility and can produce a fuller sound with less manual
    instrument adjustment.

Users may select the synthesizer engine that best suits the song,
SoundFont collection, and preferred sound.


MICROPHONE, CALIBRATION, AND RECORDING
--------------------------------------

KaraokeHD includes local microphone monitoring, singing-score support,
and a built-in performance recorder.

The recorder can capture:

- Instrumental or music-only performance
- Instrumental or music together with the singer's microphone vocal

KaraokeHD automatically calibrates its microphone processing according
to the user's device and audio hardware. This helps compensate for
device-specific audio timing and allows microphone monitoring to operate
with near-zero perceived latency on supported devices.

Actual latency may still depend on the Android device, connected
microphone, audio interface, Bluetooth connection, and selected audio
route. A wired microphone or compatible low-latency audio device normally
provides the best monitoring result.

The microphone may also be used for:

- Live vocal monitoring
- Singing-score input
- Combined music-and-vocal recording
- Wireless microphone input from the KaraokeHD Remote companion app


BACKGROUND VIDEO MANAGER
------------------------

KaraokeHD includes a Background Video Manager for organizing and
controlling the videos shown on the karaoke stage.

Background videos may be used in two ways:

GENERAL
    Videos are available as general rotating backgrounds and may play
    during any song.

ASSIGNED ONLY
    A specific background video may be assigned to one song or to a
    selected group of songs. The assigned video will play only when one
    of those songs is active.

The manager supports many-to-many assignments:

- One background video may be assigned to multiple songs.
- One song may have multiple assigned background videos.
- Unassigned songs may continue using the general background collection.
- A song-specific assignment takes priority over the general rotating
  background.

This allows users to prepare matching background videos for individual
performers, genres, events, or selected songs without affecting the
backgrounds used by the rest of the karaoke library.


KARAOKEHD REMOTE
----------------

A separate KaraokeHD Remote companion APK is also available.

Besides the basic functions expected from a karaoke remote, it provides
many advanced features, including:

- Remote song browsing, selection, queueing, and playback control
- MIDI and KAR uploading to the KaraokeHD Player
- MIDI and KAR lyrics editing inspired by Karakan
- Front- and rear-camera video background sources
- MusicXML opening, rendering, playback, and real music-sheet display
- Wireless microphone operation
- Advanced MIDI, audio, display, and player controls

Many of KaraokeHD's advanced companion and control features are available
through the Remote APK.


INITIAL INSTALLATION
--------------------

1. On first setup, select the main storage location.

2. KaraokeHD will automatically create its working structure inside the
   selected location:

   KaraokeHD/
   `-- karaoke/
       |-- sf2/
       |-- background/
       `-- karaoke/

   Folder purposes:

   sf2/
       Stores the SoundFont files used for MIDI and KAR playback.
       Multiple SF2 files may be placed in this folder.

   background/
       Stores background_zzz and place MIDI or
     KAR files inside them; or

   - Put bulk ZIP packages containing MIDI or KAR songs inside any of
     those song folders.

4. During initial setup, KaraokeHD builds its working structure and
   creates the song index:

   karaokeHD.db

   KaraokeHD may restart several times while building and verifying its
   initial structure. This is normal during the first setup.

5. At least one MIDI or KAR file must be available during initialization.

   If KaraokeHD does not detect any MIDI or KAR file, setup will display
   an error and the song index cannot be completed.

   To continue:

   - Add at least one MIDI or KAR file to the inner karaoke folder.
   - Restart KaraokeHD.
   - Run the initial setup again.

   Only one valid MIDI or KAR file is required to initiate the system.

6. After KaraokeHD has loaded, copy the required .sf2 SoundFont files
   into:

   KaraokeHD/karaoke/sf2/

   Then open:

   System > Technical Info > Select SF2

   Only SoundFont files stored inside the designated sf2 folder will be
   available to KaraokeHD.

   Select and verify the available SF2 files. KaraokeHD will catalog their
   banks, programs, and instruments so they can be used by its Multi-SF2
   system.

   The system must restart again after the SF2 setup is completed.

7. Put background videos inside:

   KaraokeHD/karaoke/background/

   During the first boot, the video stage may remain black because the
   background video library has not yet been initialized.

   To initialize and index the background videos, open:

   System > Video > Scan

   After the scan is completed, the detected videos will become available
   in the Background Video Manager.

   Background videos may then be used as general rotating backgrounds or
   assigned to specific songs or groups of songs. A video marked for
   assigned-only use will play only when one of its assigned songs is
   active.


IMPORTANT NOTES
---------------

- The APK size is more than 300 MB mainly because two offline AI models
  are included.

- AI vocal separation and Enhanced LRC creation work locally on the
  device without sending the user's songs to an online service.

- The user should process only MP3 files that they legally own or are
  authorized to use.

- At least one valid MIDI or KAR file is required during the initial
  song-library setup.

- Only SF2 files stored inside the designated sf2 folder can be selected
  and added to the instrument catalog.

- KaraokeHD can use multiple SF2 files. Different instruments from
  different SoundFonts may be assigned across the 16 MIDI channels.

- Microphone calibration is device-dependent. Wired or low-latency audio
  hardware is recommended for the best live-monitoring result.

- The recorder can save an instrumental or music-only performance, or a
  complete performance containing both the music and microphone vocal.

- The Background Video Manager supports song-specific and many-to-many
  assignments. One video may be linked to several songs, and one song may
  use several assigned videos.

- Background videos must be stored inside the designated background
  folder and scanned before they can be used or assigned.

- Several automatic restarts may occur while KaraokeHD creates its
  directories, builds karaokeHD.db, verifies the SF2 catalog, and
  initializes its components.

- These repeated initialization steps are normally required only during
  the first installation.
