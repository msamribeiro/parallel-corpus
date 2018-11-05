The Parallel Audiobook Corpus (version 1.0) is a collection of parallel readings of audiobooks. The corpus consists of approximately **121 hours of data** across 4 books and 59 speakers.

The key difference with respect to similar databases is the parallel nature of the data. The same textual source is read separately by multiple speakers.

Audio data is extracted from LibriVox: https://librivox.org

Textual data is taken from Project Gutenberg: https://www.gutenberg.org

## Table of Contents

1. [Applications](#applications)
2. [Contents](doc/contents)
3. [Data Overview](#data-overview)
4. [File Formats](#file-formats)
5. [Data Sources](#data-sources)
6. License
7. Citation
8. [Download](#download)
9. References
10. Acknowledgements

------

## Applications

The Parallel Audiobook Corpus was prepared mainly with two scenarios in mind: Speech Synthesis and Voice Conversion.

In the context of Speech Synthesis, this type of data could be useful, for example, for prosody analysis and/or evaluation. Some speakers read the stories or simulate character voices in different ways. Multiple readings of the same textual source can be useful to compare overall prosodic variation across speakers.

In the context of Voice Conversion, parallel data is essential for robust acoustic models. The segmented version of this data is conveniently prepared for this scenario. Matching utterance IDs across multiple speakers will result in a large parallel corpus for average voice models. See `utt2spk` for readings across speakers.

These are, of course, many other possibilities. Feel free to use the data according to your interests. I would be happy to hear about the various scenarios you might use this data for.



## Data Overview

Brief overview of available data per book in terms of number of speakers and hours of speech. Note that the identifier `various` denotes a book reading performed by multiple speakers, rather than a single speaker reading the book from beginning to end. Although a reading with multiple speakers is complete with respect to the book, it is not parallel within itself.

Hours of speech was estimated with Voice Activity Detection (VAD) on the Segmented Data using the tools available in [2, 3].



#### Emma

|                                 |             |
| ------------------------------- | ----------- |
| Complete book readings          | 6           |
| Readings from single speaker    | 5           |
| Readings from multiple speakers | 1           |
| Total speakers                  | 8           |
| Reading: `ekl` - 1 speaker      | 7.65 hours  |
| Reading `mfo`  - 1speaker       | 8.64 hours  |
| Reading `mth` - 1speaker        | 7.84 hours  |
| Reading `scr` - 1 speaker       | 9.81 hours  |
| Reading `sde` - 1 speaker       | 7.18 hours  |
| Reading `various` - 3 speakers  | 8.45 hours  |
| Total speech hours              | 49.57 hours |

#### Huck

|                                 |             |
| ------------------------------- | ----------- |
| Complete book readings          | 5           |
| Readings from single speaker    | 4           |
| Readings from multiple speakers | 1           |
| Total speakers                  | 21          |
| Reading: `acr`- 1 speaker       | 5.95 hours  |
| Reading `jgr`- 1 speaker        | 6.00 hours  |
| Reading `msm`- 1 speaker        | 5.94 hours  |
| Reading `pch`- 1 speaker        | 6.10 hours  |
| Reading `various` - 17 speakers | 5.14 hours  |
| Total speech hours              | 29.13 hours |

#### Sherlock

|                                 |             |
| ------------------------------- | ----------- |
| Complete book readings          | 4           |
| Readings from single speaker    | 3           |
| Readings from multiple speakers | 1           |
| Total speakers                  | 14          |
| Reading `dcl`- 1 speaker        | 5.97 hours  |
| Reading `msm`- 1 speaker        | 6.60 hours  |
| Reading `rgo`- 1 speaker        | 7.13 hours  |
| Reading `various` - 11 speakers | 5.68 hours  |
| Total speech hours              | 25.38 hours |

#### Treasure

|                                 |             |
| ------------------------------- | ----------- |
| Complete book readings          | 4           |
| Readings from single speaker    | 3           |
| Readings from multiple speakers | 1           |
| Total speakers                  | 16          |
| Reading `apr`- 1 speaker        | 4.53 hours  |
| Reading `ksh`- 1 speaker        | 3.80 hours  |
| Reading `msm`- 1 speaker        | 4.70 hours  |
| Reading `various`- 13 speakers  | 4.05 hours  |
| Total speech hours              | 17.08 hours |



## File Formats

This dataset consists only of text and waveform files. All files not ending with *.wav can be interpreted as text files.

The ctm alignment provided with the chapter-level data can be parsed as follows:

The *first field* gives the utterance ID. In this field, ses gives the audio file (which is a chapter), and the seg fields give the start and end of the utterance within the complete audio file, in 100ms units. The *second field* is the waveform channel (which is constant in this case). The *third and fourth fields* are the word start time and duration, respectively. Word start time and duration are given with respect to the beginning of the utterance, in seconds.

See [here](http://www1.icsi.berkeley.edu/Speech/docs/sctk-1.2/infmts.htm) for further details on parsing the ctm format.

## Data Sources

The three letter identifiers used in the data denote the speaker. Identifiers are determined by the speaker's username on Librivox. The identifier `various`indicates a reading performed by multiple speakers.

Please note: the links given in this section point to the original unprocessed data sources on Librivox and Gutenberg. To get the processed and aligned parallel audiobook corpus, see [download](#download).



| Emma      |                                                             |
| --------- | ----------------------------------------------------------- |
| `sbe`     | [audio](https://librivox.org/emma-by-jane-austen)           |
| `scr`     | [audio](https://librivox.org/emma-by-jane-austen-solo)      |
| `ekl`     | [audio](https://librivox.org/emma-version-3-by-jane-austen) |
| `mfo`     | [audio](https://librivox.org/emma-by-jane-austen-2)         |
| `mth`     | [audio](https://librivox.org/emma-version-6-by-jane-austen) |
| `various` | [audio](https://librivox.org/emma-version-4-by-jane-austen) |
| -         | [text](https://www.gutenberg.org/files/158/158-0.txt)       |



| Huck      |                                                              |
| --------- | ------------------------------------------------------------ |
| `acr`     | [audio](https://librivox.org/the-adventures-of-huckleberry-finn-by-mark-twain) |
| `msm`     | [audio](https://librivox.org/the-adventures-of-huckleberry-finn-by-mark-twain-version-2) |
| `jgr`     | [audio](https://librivox.org/adventures-of-huckleberry-finn-by-mark-twain) |
| `pch`     | [audio](https://librivox.org/the-adventures-of-huckleberry-finn-version-6-by-mark-twain) |
| `various` | [audio](https://librivox.org/the-adventures-of-huckleberry-finn-version-3) |
| -         | [text](https://www.gutenberg.org/files/76/76-0.txt)          |



| Sherlock  |                                                              |
| --------- | ------------------------------------------------------------ |
| `rgo`     | [audio](https://librivox.org/the-adventures-of-sherlock-holmes-by-sir-arthur-conan-doyle) |
| `msm`     | [audio](https://librivox.org/the-adventures-of-sherlock-holmes-by-sir-arthur-conan-doyle-2) |
| `dcl`     | [audio](https://librivox.org/the-adventures-of-sherlock-holmes-version-4-by-sir-arthur-conan-doyle) |
| `various` | [audio](https://librivox.org/the-adventures-of-sherlock-holmes) |
| -         | [text](http://www.gutenberg.org/cache/epub/1661/pg1661.txt)  |



| Treasure  |                                                              |
| --------- | ------------------------------------------------------------ |
| `apr`     | [audio](ttps://librivox.org/treasure-island-by-robert-louis-stevenson-2) |
| `msm`     | [audio](https://librivox.org/treasure-island-version-4-by-robert-louis-stevenson) |
| `ksh`     | [audio](https://librivox.org/treasure-island-by-robert-louis-stevenson-5) |
| `various` | [audio](https://librivox.org/treasure-island-by-robert-louis-stevenson) |
| -         | [text](https://www.gutenberg.org/files/120/120-0.txt)        |

## Download