# OME Plugins
## Modules
### DAMONITU v2.1.0

[Damonitu]: https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Damonitu"

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

