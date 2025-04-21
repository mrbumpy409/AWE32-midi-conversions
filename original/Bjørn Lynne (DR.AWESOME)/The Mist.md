# The Mist

* Requires GM bank: **yes**

## Original Text File
```
                             * The Mist *

              By Bjorn Lynne for the SB AWE32 / 2MB DRAM

This song uses it's own SoundFont file that must be uploaded to the
AWE32's RAM before playing the song. The soundfont is almost 2 MB big,
so you need at least 2 MB RAM on your AWE32. (The standard is 512kb).

If you like this song, well there's more where it came from, check in
on my homepage for cool AWE32 (and other) music:
http://www.team17-com/~bjorn

If you're a game developer, and looking for some kick-ass game music,
get in touch! I'm at bjorn@team17.com, and I've got lots of experience
with game music for PC, Playstation (have development kit), and other
platforms.

Now. How to install the soundfont and play the song...

1) Start the AWE32 Control Panel.

2) Make sure it's set to GM, *not* GS, as you need all the RAM for
   the SoundFont file.

3) In User Bank 1, locate the "AWEMIST.SBK" file, and double-click on
   it to uplod it to the soundcard's RAM.

4) Now play the song from any MIDI player, like MediaPlayer or
   Cakewalk*.

* If you use Cakewalk, you will also need to change the way that
Cakewalk handles bank-changes. Go to the Settings menu and select
Instruments, Define Instruments, Bank Select Method = "Controller 0
Only". You only need to do this ONCE, so if you've done it before,
forget it.

Note that this music is *not* Public Domain in the sense that you can
use it for whatever you want. It is provided for your personal
listening only, and should not be used for any project, commercially
or non commercially. This goes both for the song itself, AND for the
instruments contained in the .SBK file!

                              Contact:
                              --------
                             Bjorn Lynne
                           Team17 Software
                           Longlands House
                            Wakefield Rd.
                         Ossett, West Yorks.
                               WF5 9JS
                               ENGLAND

                       Email: bjorn@team17.com
                WWW : http://www.team17.com/~bjorn
```
## Conversion Notes

### SoundFont

* Added missing GM drum kit sounds from `synthgs-sf2_04-compat.sf2` to support SoundFont 1.0/2.0 preset fallback mechanism.
