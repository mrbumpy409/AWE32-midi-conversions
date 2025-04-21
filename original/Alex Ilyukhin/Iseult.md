# Iseult

* Requires GM bank: **no**

## Original Text File
```
                   -------------------
                   -== I s e u l t ==-
                   -------------------

            (C) 1997, HUT music, AlEx Ilyukhin.
            email: ai@rgti.spb.su

            Dedicated: Lani Adler (ladler@gate.net).

            Only for Sound Blaster AWE32.
            Sound Bank #1: iseult.sbk
```
## Conversion Notes

### MIDI File

* Fixed track 11 (channel 10) trying to access the wrong preset in the MIDI file.
* Fixed track 13 (channel 9) trying to access nonexistent preset. There are no notes on this channel, but removing the bank/preset select events eliminates any "preset not found" errors in the MIDI player.

### SoundFont

* Increased the release time on some instruments from 0.001 to 0.050 or 0.100 and fixed loop modes to avoid abrupt clicking on note release.
* Fixed problematic loops in the following samples and adjusted tuning:
  - **advoice**
* Fixed tuning in the following presets:
  - **000:001 ADVOIC.SDX**
  - **000:011 CHOIR.PAT**
  - **000:012 SPRNOSAX.PAT**
  - **000:015 Syn Calliope**
