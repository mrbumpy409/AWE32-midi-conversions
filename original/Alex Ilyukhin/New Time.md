# New Time

* Requires GM bank: **yes**

## Original Text File
```
                          --------------
                         -== New Time ==-
                          --------------

                (C) 1996, HUT music, AlEx Ilyukhin.

     Only for Sound Blaster AWE32.
     Sound Font Bank 1 : NEWTIME.SBK.
     E-Mail address  :  ai@rgti.spb.su
```
## Conversion Notes

### SoundFont

* Increased the release time on some instruments from 0.001 to 0.050 or 0.100 and fixed loop modes to avoid abrupt clicking on note release.
* Fixed problematic loops in the following samples and adjusted tuning:
  - advoice
  - BASS-S
* Preset **000:000 BassStation2** seems to be bugged. It features a modulation envelope pulling the pitch sharp by 131 cents. I can't imagine this is how the preset was supposed to sound, as it sound horrible within the song. I have set *Mod env → pitch (c)* to 0 to avoid this and ajusted tuning -15 cents, but this preset likely sounded quite different on the AWE32.
* Fixed tuning in preset **000:001 ADVOIC.SDX**.
* Added missing GM drum kit sounds from `synthgs-sf2_04-compat.sf2` to support SoundFont 1.0/2.0 preset fallback mechanism.
