# Anthem

* Requires GM bank: **no**

## Original Text File
```
Anthem ©1996 Ian Chisholm - Ævolution.

This track was produced on an Amiga A1200 (50Mhz 68030, 2Mb Chip 4Mb Fast RAM) 
using OctaMED v6 (© Teijo Kinnunen)

The Soundblaster AWE32 (and it's associated software) was used for MIDI.

Remixed for soundbank use 1997

MIDI Sound banks were created and edited using Vienna (© Creative Technology)

MIDI initialisation and recording was done in Cakewalk Professional v3 (© Twelve Tone 
Systems)

Soundblaster AWE32 is a copyright of Creative Labs, Inc.

Music, sequencing, production, mixing and song name - Ian Chisholm.
```
## Original Upload Text
```
Anthem - Dunno what type of music this is,
        but it certainly isn't dance
        (see, I can do other styles.)
         (mid+sbk < 512K)

©1997 Ian Chisholm - Ævolution
```
## Conversion Notes

### MIDI File

Fixed percussion channel reference to bank 1, preset 0.

### SoundFont

`Anthem.sbk` contained an entire GM bank, mostly based on `synthgm.sbk`, as far as I can tell. For the conversion, I have removed all of the presets, instruments and samples not used by the MIDI file.
