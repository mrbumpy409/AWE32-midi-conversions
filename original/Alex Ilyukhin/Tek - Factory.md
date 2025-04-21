# Tek - Factory

* Requires GM bank: **no**

## Original Text File
```
                   ---------------------
                   -== Tek - Factory ==-
                   ---------------------

            (C) 1997, HUT music, AlEx Ilyukhin.
            email: ai@rgti.spb.su

            Dedicated: Lani Adler (ladler@gate.net).

            Only for Sound Blaster AWE32.
            Sound Bank #1: tek.sbk
```
## Conversion Notes

### MIDI File

* Percussion channel was attempting to select nonexistent drum kit preset #1. Fixed to preset #0.

### SoundFont

* Fixed problematic loops in the following samples and adjusted tuning:
  - advoice
  - BASS-S
  - noname00010000
* Preset **000:000 BassStation2** seems to be bugged. It features a modulation envelope pulling the pitch sharp by 131 cents. I can't imagine this is how the preset was supposed to sound, as it sound horrible within the song. I have set *Mod env → pitch (c)* to 0 to avoid this and ajusted tuning -15 cents, but this preset likely sounded quite different on the AWE32.
