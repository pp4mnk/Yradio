# Yradio    1.9.6-1 developed by @fred181   https://forum.puppylinux.com/viewtopic.php?p=179768#p179768


YRadio is a lightweight internet radio player for Linux. Developed by @fred181. Search for stations by name or tags, select a country, or browse themed playlists to find music, news and more.  

ENGLISH/ ESPAÑOL  READme /leeME

## 🇬🇧 English

### YRadio — Internet radio player and stream recorder for Linux

**YRadio is a lightweight graphical application for discovering, listening to and recording internet radio stations.** It combines online station searches, personal playlists, favourites and stream recording in a compact desktop interface.

### Find stations and organise your listening

YRadio searches the **Radio Browser directory** directly over the internet, without requiring a full local station database.

You can:

- Search by station name or descriptive tags, including musical genres such as rock, jazz or dance.
- Use multiple search words, such as “classic rock”.
- Select a country from the dropdown menu.
- Browse the included themed playlists.
- Save search results as a new playlist.
- Create personal playlists and add or remove stations.
- Add a custom station by entering its stream URL, name and description.

Double-clicking a station starts playback. When the broadcaster supplies suitable metadata, YRadio can display the current song title and information such as the station name, genre and reported bitrate.

**Search uses station directory information.** Searching for an artist may find stations whose names or tags mention that artist; it does not provide a live search across the songs currently playing on every station.

### Record radio streams

YRadio lets you select a recording folder and remembers that location for later sessions. Recordings are organised into subfolders named after the station.

The recommended recording method uses **mpv with a Lua script**. The script monitors the stream’s title metadata and starts a new recording file when that title changes. It also adds a sequential number and replaces characters that are unsuitable for filenames.

For example, an MP3 stream might produce:

`1000 HITS 80s/001 - Tom Tom Club - Wordy Rappinghood.mp3`

**Recordings are not always MP3 files.** The script obtains the file format reported by mpv and uses it as the extension, with MP3 as a fallback if the format is unavailable. It uses mpv’s stream-recording functionality rather than providing a selectable MP3 conversion or quality-setting interface.

Track separation depends on the metadata supplied by the broadcaster. Missing, delayed or inaccurate titles can affect filenames and track boundaries. This is metadata-based splitting rather than audio recognition or precise song detection.

### Desktop integration

YRadio includes a notification-area icon with access to playback and recording functions. Its volume control uses available system audio tools, with support for ALSA controls and PulseAudio-compatible controls.

This customised PET includes the new **YRadio logo** in the application menu, the main window icon and the notification-area icon.

### Technical details

| Component | Implementation in this package |
|---|---|
| Application version | YRadio 1.9.6, packaged with customised branding |
| Main application | Bash script |
| Graphical interface | YAD |
| Playback backends | mpv or MPlayer; mpv is preferred when available |
| Recommended recording backend | mpv with the included `yradio_ripper.lua` script |
| Alternative recording backend | Streamripper, when installed and the alternative recording path is used |
| Station search | HTTPS requests to the Radio Browser API using `curl` |
| Search response processing | CSV processed with shell tools, including `awk` and `sed`; no `jq` dependency for this search implementation |
| User data | `~/.yradio/`, including playlists, player preference and temporary working files |
| Recording-folder preference | `~/.config/streamrip.conf` |
| Application directory | `/usr/local/YRadio/` |
| Distribution format | PET package intended for Puppy Linux and EasyOS |
| Version 1.9.6-4 added the use of the icon in tray.- No task bar

The original application identifies **fredx181** as its author. This customised package retains the application’s existing functionality and adds the new visual identity.

Actual station availability, playback formats and recording compatibility depend on the broadcaster, network connection and installed media backends. The PET’s structure and checksum have been checked; installation of this customised package has not yet been tested on EasyOS.

---

## 🇪🇸 Español

### YRadio — Reproductor de radio por internet y grabador de emisiones para Linux

**YRadio es una aplicación gráfica ligera para descubrir, escuchar y grabar emisoras de radio por internet.** Reúne búsqueda de emisoras, listas personales, favoritos y grabación de emisiones en una interfaz de escritorio compacta.

### Encuentra emisoras y organiza tus listas

YRadio consulta directamente el **directorio de Radio Browser** a través de internet, sin necesidad de descargar una base de datos completa de emisoras.

Permite:

- Buscar por nombre de emisora o etiquetas descriptivas, incluidos géneros musicales como rock, jazz o dance.
- Utilizar varias palabras en una búsqueda, por ejemplo, «
