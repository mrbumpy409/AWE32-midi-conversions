# AWE32 MIDI Conversions
Conversions of old AWE32 SoundFont + MIDI songs to SoundFont 2.01/2.04 spec compliance

---

## 1. About the Songs

This archive features a large collection of songs originally written for the AWE32 and Live! sound cards. The songs have been updated for correct playback on [FluidSynth](https://www.fluidsynth.org/) and other SoundFont synthesizers adhering to the SoundFont 2.01 spec or later with AWE32 NRPN support. The original versions of most of the songs were downloaded from [this archive](https://ftp.lysator.liu.se/pub/awe32/songs/) in November 2024. I have also added several others from my personal collection.

### 1.1 MIDI and SoundFont Files

The majority of these songs consist of a MIDI file and a similarly-named SoundFont that provides instrument samples required by the song. In all cases, the SoundFont is to be loaded into bank 1. Many of the songs also require a GM SoundFont to be loaded into bank 0. Depending on when and for which sound card a particular song was written, the GM bank used by the composer would have likely been one of the following:

* Composed on Sound Blaster AWE32/64:
  - `synthgm.sbk` – Contains all 127 GM melodic presets plus 1 drum kit using only samples from the onboard 1MB sample ROM.
  - `synthgs.sbk` – Contains everything in `synthgm.sbk` plus extra Roland GS presets, SFX and drum kits, which use up most of the AWE32's base 512K sample RAM.
* Composed on Sound Blaster Live!:
  - `2gmgsmt.sf2` – A complete set of Roland GS instruments and drum kits plus Roland MT-32 presets on bank 127. Uses 2MB sample RAM.
  - `4gmgsmt.sf2` – Same as `2gmgsmt.sf2` but with better quality samples. Uses 4MB sample RAM.

I have edited both `synthgs.sbk` and `4gmgsmt.sf2` to better emulate the behavior of the old cards when played on a synthesizer adhering to the SoundFont spec version 2.01 or newer. These conversions can be found in the `gm-soundfonts` folder as `synthgs-sf2_04-compat.sf2` and `4gmgsmt-sf2_04-compat.sf2` respectively. Of course, you can use any GM bank you desire, but be aware that reverb and chorus controller sensitivity will usually be lower for other GM banks vs. how they would have sounded on an AWE32 or Live! sound card. The one exception I am aware of is my own GM SoundFont [GeneralUser GS](https://www.schristiancollins.com/generaluser), in which I have boosted the effects levels much closer to what you would get from an AWE32 or Live! sound card.

So, my recommended GM SoundFonts to use for playing the songs in this collection are:
* For songs composed on Sound Blaster AWE32/64: `synthgs-sf2_04-compat.sf2`
* For songs composed on Sound Blaster Live!: `4gmgsmt-sf2_04-compat.sf2`
* If you want higher quality GM voices: [GeneralUser GS](https://www.schristiancollins.com/generaluser) v2.0 or later

Also be sure to read the **\*.md** notes file accompanying each song to see if the composer has any directions regarding the GM bank and whether or not a song actually uses GM instruments.

All of the conversion steps listed in [section 3](#3-converting-the-songs-for-playback-on-modern-systems) below have been made to the SoundFonts contained in this archive, but there will be occasional errors. It's likely that most differences and errors will be impossible to identify without recordings of the songs on original hardware. So, if anybody out there has a Sound Blaster AWE32 or AWE64 that they can record and sufficient free time and desire, your efforts would be hugely appreciated! Submitted recordings will be included in the archive and will aid in fixing any remaining compatibility issues with the converted SoundFonts. You can submit your AWE32/64 recordings [here](https://github.com/mrbumpy409/AWE32-midi-conversions/issues/1).

### 1.2 File Organization

The root directory contains the following folders:

* `gm-soundfonts` – AWE32 and SB Live! GM banks edited to provide a more authentic sound.
* `jazz` – Performances of known jazz works
* `misc` – Songs that I wasn't able to categorize
* `original` – Songs that were composed for the AWE32 or SB Live!, organized by artist
* `popular` – Covers and recreations of pop and rock favorites, organized by artist

Each song may consist of one or more of the following files:

* `Song Name.md` – Information about the song and its conversion, including a copy of the original, accompanying text file(s).
* `Song Name.mid` – The MIDI file used to play the song.
* `Song Name.OLD.mid` – If I have altered or corrected a MIDI file, this will be the original version.
* `Song Name.sf2` – The song's SoundFont converted to version 2.01/2.04 spec compliance. This should be loaded to bank 1 for correct song playback.
* `Song Name.OLD.sbk` – The original version of the song's SoundFont (SoundFont 1.0)
* `Song Name.OLD.sf2` – The original version of the song's SoundFont (SoundFont 2.0)
* `Song Name.wrk` – A version of the song in Cakewalk format. In cases where a song was only released in this format, I have converted the .wrk file to MIDI (.mid) using Cakewalk. There should be no reason to play the Cakewalk version of the song.

## 2. Playing the Songs

The songs in this collection are playable on the following SoundFont synthesizers:
* [FluidSynth](https://www.fluidsynth.org/) 2.4.5 or later
* Possibly [BASSMIDI](https://www.un4seen.com/) (needs testing)
* Sound Blaster Audigy/Audigy2/X-Fi hardware SoundFont synthesizers
* Sound Blaster AWE32, AWE64 and Live! (use the version of the song's SoundFont that has ".OLD" in the filename)

Instructions for each synthesizer are listed below.

### 2.1 FluidSynth

1. Download and install [FluidSynth](https://www.fluidsynth.org/) 2.4.5 or later for your system. If you are on Windows, you may need to manually add the FluidSynth executable path to your system path variable.
2. To better emulate the AWE32's reverb and chorus settings, place the following into the FluidSynth config file (`$HOME/.fluidsynth` on Linux and macOS, `%USERPROFILE%\fluidsynth.cfg` on Windows):
   ```
   # AWE32 MIDI FX settings:
   set synth.reverb.damp 0.3
   set synth.reverb.level 0.6
   set synth.reverb.room-size 0.65
   set synth.reverb.width 0.8
   set synth.chorus.depth 4.7
   set synth.chorus.level 0.43
   set synth.chorus.nr 3
   set synth.chorus.speed 0.4
   ```
3. Determine which song you would like to play.
4. Determine if the song has its own SoundFont bank (e.g., `Cool Song.mid` is accompanied by `Cool Song.sf2`).
5. Open a terminal and play the song using the following command formula (assuming the song name `Cool Song.mid` and GM SoundFont name `GM SoundFont.sf2`):
   ```
   fluidsynth "/path/to/GM SoundFont.sf2" "/path/to/Cool Song.mid"
   ```
   See [section 1.1](#11-midi-and-soundfont-files) above for recommended GM SoundFonts.

6. When FluidSynth starts, it will begin playing the MIDI file immediately. If the song has its own SoundFont bank, however, additional steps will be needed:
   1. Stop the player by typing the following into FluidSynth's console:
      ```
      player_stop
      ```
   2. Load the song's SoundFont into bank 1 using a command in the following format:
      ```
      load "/path/to/Cool Song.sf2" 1 1
      ```
   3. Then, restart the player:
      ```
      player_start
      player_cont
      ```

Here are some helpful tips to make all of this a bit easier:

* Navigate to the song's folder in the terminal using the `cd` command. Then, you will not need to specify file paths for the song's MIDI or SoundFont files.
* If the song doesn't require a GM bank, you can load the song's SoundFont to bank 0 instead and it will play back just fine. Read the song's accompanying **\*.md** notes file to determine if a GM bank is needed for playback, and if not, you can simply play the song as follows:
  ```
  fluidsynth "/path/to/Cool Song.sf2" "/path/to/Cool Song.mid"
  ```
* Quotes are required around the SoundFont or MIDI file name only if there are spaces in the file path.
* If you'd rather not specify the GM bank manually each time, you can place it in the FluidSynth config file in step 2 as follows:
  ```
  set synth.default-soundfont "/path/to/GM SoundFont.sf2"
  ```

### 2.2 Other SoundFont Synths

_**TODO:** The documentation for playback on other SoundFont synths still needs to be written._

## 3. Converting the Songs for Playback on Modern Systems
  
### 3.1 History

The Sound Blaster AWE32 was released in 1994, introducing E-Mu's SoundFont technology to the world and making sample-based audio synthesis more accessible to the home musician. Many people—myself included—reveled in the opportunity to create music on our PCs using more than just stock General MIDI sounds. Though tracker musicians had already been creating sample-based music by this time, the AWE32 allowed composition using MIDI (tracker music is essentially programmed) and played the samples in hardware with very high quality resampling and a resonant lowpass filter—something only the fastest PCs of the time could accomplish in software.

Musicians ran with this new opportunity, and a new pseudo-format was born: the AWE32 MIDI (or SoundFont MIDI) song, consisting of the following components:
* A MIDI file
  - Most MIDI files would access both the General MIDI SoundFont (bank 0) and the song's custom SoundFont (bank 1). Some songs access only the custom SoundFont.
* A SoundFont file
  - Usually named identically to the MIDI file, but with .sbk or .sf2 extension.
  - Usually to be loaded into bank 1, with bank 0 containing a General MIDI SoundFont.

This format became somewhat popular for sharing AWE32 compositions over the Internet, and there were even custom AWE32 MIDI players available that would automatically detect an identically-named SoundFont and load it into bank 1.

:memo: *The AWE64—a slightly upgraded version of the AWE32—was also released in 1996, but for conciseness, any mention of AWE32 will apply to both cards.*

#### 3.1.1 First Changes to the SoundFont Format

In 1998, Creative labs released the Sound Blaster Live!, and somewhere along the way, the SoundFont standard was updated from the original 1.0 version to 2.0, bringing a new SoundFont filetype with it. The AWE32 was updated for SoundFont 2.0 compatibility, and both the Sound Blaster Live! and AWE32 could load the original 1.0 SoundFonts (with **.sbk** extension) and version 2.0 SoundFonts (with **.sf2** extension).

However, there were some behavioral changes between SoundFont 1.0 and 2.0 that did affect some of the old .sbk files. Unfortunately, this was all poorly documented, as Creative Labs had not yet released an official SoundFont spec. Personally, I can only still remember a few changes between SoundFont 1.0 and 2.0 off the top of my head:
* SoundFont 1.0 used a lot of sample ramping, IMO, even with the volume envelope set to the minimum 0.001 seconds. I remember being frustrated by the "squishy" note attack leading to a lack of punch in percussion samples. This was fixed in SoundFont 2.0, with no sample ramping applied when setting note attack between 0.001 and 0.005 seconds.
* SoundFont 1.0 (at least via Vienna SoundFont Studio) only allowed up to 8,000 Hz for the filter cutoff value, which was actually fully open on the AWE32's unique lowpass filter. This limit was removed in SoundFont 2.0.
* Using the third-party .sbk editor "Esbeekay", I was able to make a preset play the entire contents of the sample ROM with a single keypress. I don't know if anybody else ever discovered this, and SoundFont 2.0 made this no longer possible.
* SoundFont 1.0 was closely tied to the AWE32 hardware, and this included the use of the 1 MB sample ROM that was present on all AWE cards. Starting with the Sound Blaster Live!, this ROM was no longer physically present, but instead supplied in software in the Creative drivers for backwards compatibility.

Ultimately, most AWE32 songs still played just fine on a Sound Blaster Live! But everything changed ~~when the fire nation attacked~~ with the release of the E-Mu APS and its accompanying SoundFont 2.01 standard.

#### 3.1.2 SoundFont 2.01/2.04 

In 1998, E-Mu Systems released the Audio Production Studio (or APS), a sound card designed for professional music production. The APS featured a new SoundFont revision, version 2.01, and for the first time, an official specification was also published. The Sound Blaster Audigy released in 2001 would also utilize this new SoundFont revision, as would the Audigy2.

SoundFont 2.01 made several improvements over 2.0, most notably support for modulators. Being able to control how different MIDI sources would modulate synthesizer parameters gave SoundFont 2.01 very powerful capabilities, though these features were often underutilized by SoundFont creators. SoundFont 2.04 was released along with the Sound Blaster X-Fi in 2005, adding support for 24-bit samples and altering the behavior of the default velocity-to-filter cutoff modulator. Otherwise, 2.01 and 2.04 are functionally equivalent, as far as I am aware.

While SoundFont 2.01/2.04 is considered to be backwards-compatible with 2.0 SoundFonts, the behavioral changes in 2.01 (especially regarding default modulators) require some manual steps to be taken when preparing AWE32 & Live! MIDI + SoundFont songs for accurate playback on SoundFont 2.01/2.04-compliant devices. Songs that use version 1.0 .sbk files require even more work, as detailed in the following section.

### 3.2 Updating the SoundFonts for Playback on Modern Systems

#### 3.2.1 Converting SoundFont 1.0 to 2.0

SoundFonts in SoundFont 1.0 format (.sbk) must first be converted to 2.0 (sf2). To my knowledge, this is best done using "SoundFont Librarian" by E-mu, which requires a legacy Windows OS setup that can run 16-bit applications. I set up a Windows 98 virtual machine for this purpose and then used SoundFont Librarian to convert all of the .sbk files to .sf2, making RAM copies of all referenced AWE32 ROM samples. This latter step is required for playback on modern SoundFont synthesizers.

There are sometimes errors in the SoundFont conversion. These can be hard to identify and/or fix without a recording of the song played on actual AWE32 hardware. Because of that, there are likely such errors in this collection. For example, I discovered an error in the SoundFont for *Tekkniko* by Niko Boese thanks to a YouTube recording of the song played on AWE32. Investigating the SoundFont, I found that one instrument was playing inaudably 5 octaves below its correct pitch.

Once a SoundFont is in 2.0 format, it will need further measures taken to ensure 2.01/2.04 compliance.

#### 3.2.2 Converting SoundFont 2.0 to 2.01/2.04

The following changes must be made to a 2.0 SoundFont in order for it to sound correct on a 2.01/2.04 compliant synthesizer:

* Disable default *velocity→filter cutoff* modulator for each instrument (both 2.01 and 2.04 spec versions of the modulator).
* Enable *velocity→filter cutoff* modulator (2.04 spec version) for any samples with volume envelope attack at 0.008 seconds or greater. Note that no modulator can accurately replicate the curve used in SoundFont 1.0/2.0, so affected instruments can either sound too bright or too dark depending on how they're used.
* Re-route mod wheel (CC1) and channel aftertouch to modulate modLFO (LFO1) instead of vibLFO (LFO2).
* Increase reverb (CC91) and chorus (CC93) controller sensitivity to 40% to better match AWE32 fx levels when using Audigy or FluidSynth (default 2.01/2.04 value is 20%). It is also important to configure the SoundFont synth with ideal reverb and chorus settings (see [section 2](#2-playing-the-songs)).
* Replace ROM samples with RAM copies.
* In SoundFont 1.0 and 2.0, if note was played on a drum kit (MIDI channel 10) on bank 1 or higher that didn't have an assigned sample in the preset, the corresponding note from bank 0 would be played instead. This is not true for SoundFont 2.01/2.04 devices, where the notes missing from the bank 1 preset will just play silence. Some AWE32 songs rely on this behavior, so the missing percussion sounds must be copied into the SoundFont's percussion preset from a GM bank.

#### 3.2.3 Other Considerations

* Many converted SoundFont 1.0 instruments have a volume envelope attack of 6 ms, though the composer may have preferred a faster attack were it possible on the early SoundFont version. This notably leads to "squishy" attacks on percussion instruments. Each song would need to be evaluated for possible attack value alteration to improve the sound.
* Some AWE32 songs use filter NRPN commands to set the filter fully open for a track, but make no use of filter modulation otherwise. In such cases, an "open" filter is at around 8,000 Hz, which when played on modern SoundFont engines (e.g., FluidSynth, BASSMIDI) is not actually fully open. In these cases, it will be necessary to remove the filter NRPN command and verify that the referenced SoundFont preset has an open filter for the best sound.

## 4. Final Notes

All of this documentation was written quickly and may contain errors; I will try to improve it as I have time. If you find issues with either the documentation or the songs themselves, please file a bug report. I haven't had time yet to listen to all of the converted songs in this archive, so it is likely that more work will be needed.
