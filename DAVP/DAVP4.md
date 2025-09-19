# DAVP4
## Table of Contents
- [DAVP4](#davp4)
  - [Table of Contents](#table-of-contents)
  - [REAPER](#reaper)
    - [What is Reaper](#what-is-reaper)
    - [Interface Overview](#interface-overview)
    - [Working with Audio Files](#working-with-audio-files)
    - [Recording Setup](#recording-setup)
    - [Playback Controls](#playback-controls)
    - [Project Settings](#project-settings)
    - [Editing Items](#editing-items)
    - [Track Management](#track-management)
    - [Effects (FX)](#effects-fx)
    - [MIDI Files](#midi-files)
    - [Saving and Exporting](#saving-and-exporting)

## REAPER

- See REAPER Cheatsheet.pdf
- See REAPER Quick Start,pdf

### What is Reaper
- Complete multi-track Digital Audio Workstation (DAW)
- Manages, edits, and combines samples, recordings, and MIDI compositions
- Available for Windows, MacOS, and Linux
- 60-day free trial before license required

### Interface Overview
- Timeline/Arrangement window on top
- Mixer at bottom
- Timeline shows time in bars/beats (top) and seconds (bottom)
- Can change colors/style via Options > Themes

### Working with Audio Files
- Import by drag and drop onto timeline
- Can import videos too (View > Video)
- Files appear as "Items" showing waveforms
- Items organized in "Tracks" (rows)
- Use mouse wheel + CTRL/CMD to extend tracks
- Zoom in/out with mouse wheel on green playhead
- Hold ALT/Option + mouse wheel to scroll through time

### Recording Setup
- Go to Options > Preferences > Device
- Set Audio system (WaveOut for default, ASIO for professional low-latency)
- Select Input device (microphone/external instrument)
- Select Output device (speakers)
- Right-click left panel to insert new track
- Click Record Arm to enable track for recording
- Keep Record Monitoring ON to hear input (watch for feedback)
- Click timeline to set start point, use Record button to start/stop

### Playback Controls
- Use player controls on left
- Spacebar to play/stop
- Enter key to play/pause
- Click and drag above timeline to create loop region
- Enable Toggle Repeat for loop playback

### Project Settings
- Set tempo in BPM (beats per minute)
- Define time signature (beats per bar)
- Use Rate knob for different playback rate
- Click "i" button for advanced settings (sample rate, recording options)

### Editing Items
- Click and drag to move items in time or between tracks
- Snaps to grid (Options > Snap/Grid) unless holding Shift
- Press N for precise nudge dialog
- Drag edges to adjust length (cuts content when shortened, loops when extended)
- Hold ALT/Option while dragging edges to change speed instead of length
- Pull down top line to adjust volume
- Drag corners to add fade transitions
- Select item and use CTRL/CMD + X/C/V to cut/copy/paste
- Hold CTRL/CMD while moving to duplicate
- CTRL/CMD + Z to undo
- Place playhead and press S to split selected item
- Double-click item to see properties
- Hold CTRL/CMD while clicking to select multiple items

### Track Management
- M button to mute track
- S button to solo track (mutes all others)
- Check volume levels with decibel meter (avoid red saturation)
- Main bar adjusts track volume
- Panning knob balances left/right stereo channels
- Master track affects entire audio output
- Right-click track to add/remove/duplicate

### Effects (FX)
- Click FX button to add effects
- Includes VST and JS (Jesusonic) plugins
- Available effects: Reverb, Saturation, Pitch, Delays, EQ filters
- Click checkmark to enable/disable effects
- Drag to reorder effects
- Remove button deletes selected effect
- I/O button next to FX disables all track effects
- Trim button enables envelopes to change properties over time
- Edit envelope points by pulling up/down
- Hold CTRL/CMD while brushing to edit envelope shape
- ALT/Option + click to remove envelope points
- Bypass button hides envelopes

### MIDI Files
- Import by drag and drop
- May offer options to extract tracks or match tempo
- Must assign instruments to MIDI tracks via FX > Instruments
- ReaSynth for melodic sounds
- ReaSynDr for percussion/drums
- Right-click > Insert virtual instrument for new track with synth
- Hold CTRL/CMD and drag to create new MIDI item
- Press E or double-click to open Piano Roll editor
- Click piano keys to test sounds
- Click and drag in Piano Roll to place notes
- Move notes by dragging (changes time and pitch)
- Drag note edges to adjust length
- Pull down top line to adjust velocity
- Use CTRL/CMD + X to cut/remove notes
- Bottom panel adjusts note properties
- Hold CTRL/CMD to draw velocity envelopes
- ALT/Option to remove envelope points

### Saving and Exporting
- File > Save project as... creates .RPP files (stores entire timeline)
- File > Render... exports as audio file
- Select Master mix for full output
- Choose export bounds (entire project, loop region, time selection)
- Set directory, filename, sample rate, channels
- File formats: WAV, FLAC, MP3 for audio; GIF, AVI, FLV, MP4 for video
- Control bitrate, frame size, and frame rate for video exports