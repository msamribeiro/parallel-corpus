## File Formats

This dataset consists only of text and waveform files. All files not ending with *.wav can be interpreted as text files.

The ctm alignment provided with the chapter-level data can be parsed as follows:

The *first field* gives the utterance ID. In this field, ses gives the audio file (which is a chapter), and the seg fields give the start and end of the utterance within the complete audio file, in 100ms units. The *second field* is the waveform channel (which is constant in this case). The *third and fourth fields* are the word start time and duration, respectively. Word start time and duration are given with respect to the beginning of the utterance, in seconds.

See [here](http://www1.icsi.berkeley.edu/Speech/docs/sctk-1.2/infmts.htm) for further details on parsing the ctm format.

