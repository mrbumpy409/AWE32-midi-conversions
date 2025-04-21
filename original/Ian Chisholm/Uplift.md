# Uplife

* Requires GM bank: **yes**

## Original Text File
```
Uplift ©1996 Ian Chisholm - Ævolution.

Use Room 3, Chorus 1 in the control panel

This track was produced on an Amiga A1200 (50Mhz 68030, 2Mb Chip 8Mb Fast RAM) 
using OctaMED v6 (© Teijo Kinnunen)

The Soundblaster AWE32 (and it's associated software) was used for MIDI.

This is the Fourth AWE32 MIDI track produced by Ævolution.

Most samples were sourced from the public domain, and converted / edited using Goldwave (© 
Chris S. Craig.)

MIDI Sound banks were created and edited using Vienna (© Creative Technology)

MIDI initialisation and recording was done in Cakewalk Professional v3 (© Twelve Tone 
Systems)

Soundblaster AWE32 is a copyright of Creative Labs, Inc.

Music, sequencing, production, mixing and song name - Ian Chisholm.


* Not yet finished *
```
## Original Upload Text
```
Uplift - Active Dance Track
                MID + <512K sbk

I found the lowpass filter!

©1997 Ian Chisholm - Ævolution
```
## Conversion Notes

### MIDI File

* Fixed the quantization errors that caused frequent "hiccups" in the tempo. It's possible that a few errors might remain, but not enough to be noticeable.
* Fixed percussion channel reference to bank 1, preset 0.

### SoundFont

* Fixed the following samples in the SoundFont, which had out-of-spec loop points (e.g., loop end was set beyond the end of the sample) leading to out-of-tune playback:
  - SAWTOOTH
  - SQUARE1
  - SQUARE2
  - SQUARE3
  - SQUARE4
  - W12_1
  - W12_2
  - W12_4
  - W13_3
* As a result of fixing the loop points in the above samples, they also had to be re-tuned. The instruments containing these samples now play in tune, but if there was any deliberate detuning in the original preset versions, this has been lost. Only access to an AWE32 might reveal the truth.
* Added missing GM drum kit sounds from `synthgs-sf2_04-compat.sf2` to support SoundFont 1.0/2.0 preset fallback mechanism.
