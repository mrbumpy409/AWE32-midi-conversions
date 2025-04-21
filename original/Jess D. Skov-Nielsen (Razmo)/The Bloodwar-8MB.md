# The Bloodwar - 8 MB version

* Requires GM bank: **no**

The 8 MB version of *The Bloodwar* was distributed with the MIDI in Cakewalk .wrk format and required the use of two SoundFont synthesizers in order to have enough MIDI channels available. I combined the events on the 22 used MIDI channels to fit into 16 channels when converting from .wrk into .mid format. If playing using the original files, you will need to use both synth engines on a Sound Blaster Live! or Audigy sound card, and the SoundFont must be loaded onto bank 1 or 0 for both synthesizers.

Please see `The Bloodwar.md` for more information on this excellent track.

## Text from the MIDI File
```
Copyright © 1997-1998 by Jess D. Skov-Nielsen, Denmark
Email : razmo@post4.tele.dk
```
## Conversion Notes

### MIDI File

* Converted the Cakewalk .wrk file to .mid and combined MIDI events to fit onto 16 channels.
* Removed unnecessary NRPN events from the MIDI file so that filter would be fully open in FluidSynth.

### SoundFont

* Set filter fully open for all presets featured on tracks where Jess had used NRPN to set filter to max value.
