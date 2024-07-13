# OME Plugins for VCV Rack 2

## OME 2.1.0
### DAMONITU

Generates arpeggios and melodies based on euclidian ryhtmic patterns and randomizable, or fixed, melodic patterns. This module belongs to the heptatonic club.

* Tempo knob. 
  * Sets internal clock’s BPM.
* Tempo input and trimmer. 
    * Modulates internal clock’s tempo value.
* Clock, run and reset inputs.
  * Synchronize the module with external run and reset events.
* Clock light.
  * Just this, a light.
* Run and reset buttons.
  * Generates internally run and reset events.
* Knobs
  * Root.
    *Sets the root note. All knobs have an input and modulation knob.
  * Scale.
    * Sets the scale to be used. The module has thirty five modes from major, harmonic minor, melodic minor, harmonic major and double harmonic major scales.
  * Pattern.
    * Sets a pattern (non rhythmic) to be used to generate the notes. For instance, the pattern 1357F means that first, third, fifth and seventh grades of the scale in this order will be used. “F” means “forward” and “B” backward. 
    * RANDOM pattern selects the notes, in the context of the selected scale, randomly and freely. In this version these patterns are fixed. 
  * Octave. 
    * Increases or decreases the octave (-2,+2)
  * Rotate.
    * Rotates the selected pattern, for instance, if the pattern is 1357F and rotate knob has the value 1, the first note in the cycle will be 3 and so on. 
  * Chord.
    * Sets the number of notes, in the context of the selected scale, to generate chords (through chord polyphonic output). 
    * The chords generated could be a triad, 7th , 9th or 11th chords.
    * This version doesn’t support inversions and voicings.
  * Steps.
    * Sets the number of steps. 
    * If the number of steps is minor than melodic pattern's size, the melodic pattern will be truncated.
  * Density.
    * Sets the factor to generate the number of notes in the cycle. 
    * A low value will limit the range. The result will be just several notes.
    * A high value will open this range and the result could be just a several notes or a very populated pattern.
    * Internally uses random numbers uniformly distributed.
  * Display.
    * Shows the knob values.
* Outputs.
  * 1v/oct. 
    * Singe channel 1v/oct output.
  * Gate. 
    * Opened when there is a a hit in the rhythmic pattern. Closes at the end of pulse.
  * Trigger. 
    * Triggered when there is a a hit in the rhythmic pattern.
  * Chord.
    * Polyphonic chord output. The number of channels depends of chord knob value.
  * EOC.
    * End of cycle trigger.
## OME 2.2.0
### DAMONITU
![Damonitu](Damonitu220.png?raw=true "Damonitu")
* Changes
  * Fixed buggy (with crashes) CV and trims handling.
  * Density knob behavior change. Now there are no random values, the knob value (or CV+Trim) is applied directy over number of notes in the pattern.
  * Added more melodic patterns.
  * The display widget uses <code>LedDisplay</code> included in the VCV Rack components library.
### TEZCA
![Tezca](Tezca220.png?raw=true "Tezca")

Generates chord progressions using a simplistic implementation of Béla Bartók's axis system. Major scale, seven modes. [See: Axis System](https://ib-aural.com/bartoks-axis-theory/)

**WARNING!**: The results could be unfamiliar and rare ;)

* Input
  * 1v/oct. Monophonic input. Set the root note. If not connected, C4 is used.
* Knobs
  * Steps. Number of pulses before trigger transitions.
  * Chord. Number of notes in the chord. Only has effect if default voicind is used.
  * Voicing. Default, rootless, open and three notes.
  * Bass. Low note inversion.
  * Gate length. Set the gate pulse length.
* Dices (from left to right)
  * From tonic transition. Set the probability threshold to go to dominant (value) or subdominant (100-value) compass.
  * From subdominant transition. Set the probability threshold to go to tonic (value) or dominant (100-value) compass.
  * From dominant transition. Set the probability threshold to go to tonic (value) or subdominant (100-value) compass.
* Outputs
  * Chord. Polyphonic output with all chord notes.
  * Bass. Monophonic output with the lower note, an octave down.
  * Scale. Polyphonic output with all scale notes.
  * Trigger. Triggered on every clock pulse.
  * Gate. Triggered on every clock pulse.
* Settings
  * Mode transition. It has two modes.
    * Gentle. Transitions are made using "mode brightness" order. The order used is, from bright to dark: Lydian, Ionian, Mixolydian, Dorian, Aeolian, Phrygian and Locrian.
    * Rude. Random transitions. 

## OME 2.3.0
### MAŜINO
![Maŝino](Masino230.png?raw=true "Tezca")

Yet another arpeggiator with useful features.
* Inputs
  * 1v/o. Polyphonic 1v/octave input.
  * Clck. Clock.
  * Rst. Reset.
* Knobs
  * All knobs have an 0/+5v input to modulate the values. The input voltage values are quantized according the parameter range. 
  * Rythm
    *  UNF. Uniform.
    *  EUC. Euclidean.
    *  PRM. Prime numbers.
    *  WBE. Weak beats.
    *  SBE. Strong beats.
    *  RND. Random.
  * Melody
    * UPP. Upwards according to the order of the notes played.
    * DWN. Downwards according to the order of the notes played.
    * TCE. Plays the notes from the ends towards the center according to the order of the notes played.
    * FCE. Playy the notes from the center to the ends according to the order of the notes played.
    * RND. Random.
  * Octaves. Set the arpeggio octaves scope.
  * Density. Set the number of notes to be played. It doesn't affect PRM rythm setting. 
  * Gate Length. 
* Outputs
  * 1v/o. Monophonic 1v/octave output.
  * Gate.
  * Trigger.
* Settings.
  * Pulses per quarter. Sets the clock pulse subdivision. Values are 2,3,4,5 and 6 PPQN.
  * Pulses per quarter factor. Multiply PPQN value. Values are X1, X2 and X3.
 
**Important:**

**Be aware the modules chain length. Polyphonic 1v/oct and clock inputs sources should have the same length. Otherwise there may be offsets, desynchronization and undesirable results.**

### TEZCA
GUI cosmetic fixes. 
## Versions

| Date  | Changes |
| ------------- | ------------- |
| 06/09/2024  | Damonitu 2.1.0 - First Version  |
| 06/26/2024  | Damonitu 2.2.0 - Some functionality changes and fixes  |
| 06/26/2024  | Tezca 2.2.0 - First version  |
| 07/12/2024  | Tezca 2.3.0 - Cosmetic changes  |
| 07/12/2024  | Maŝino 2.3.0 - First version  |


Enjoy!

 

