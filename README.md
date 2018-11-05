The Parallel Audiobook Corpus (version 1.0) is a collection of parallel readings of audiobooks. The corpus consists of approximately **121 hours of data** across 4 books and 59 speakers.

The key difference with respect to similar databases is the parallel nature of the data. The same textual source is read separately by multiple speakers.

Audio data is extracted from LibriVox: https://librivox.org

Textual data is taken from Project Gutenberg: https://www.gutenberg.org

## Table of Contents

1. [Applications](#applications)
2. [Contents](#contents)
3. [Data Overview](#data-overview)
4. File Formats
5. Data Sources
6. License
7. Citation
8. References
9. Acknowledgements

------

## Applications

The Parallel Audiobook Corpus was prepared mainly with two scenarios in mind: Speech Synthesis and Voice Conversion.

In the context of Speech Synthesis, this type of data could be useful, for example, for prosody analysis and/or evaluation. Some speakers read the stories or simulate character voices in different ways. Multiple readings of the same textual source can be useful to compare overall prosodic variation across speakers.

In the context of Voice Conversion, parallel data is essential for robust acoustic models. The segmented version of this data is conveniently prepared for this scenario. Matching utterance IDs across multiple speakers will result in a large parallel corpus for average voice models. See utt2spk for readings across speakers.

These are, of course, many other possibilities. Feel free to use the data according to your scenario of interest. I would be happy to hear about the various scenarios you might use this data for.

## Contents

There are four audiobooks books in this dataset.

| Identifier | Book                                                     |
| ---------- | -------------------------------------------------------- |
| emma       | Emma, by Jane Austen                                     |
| huck       | The Adventures of Huckleberry Finn, by Mark Twain        |
| sherlock   | The Adventures of Sherlock Holmes, by Arthur Conan Doyle |
| treasure   | Treasure Island, by Robert Louis Stevenson               |

Each book is read by multiple speakers. The data is provided in two formats:

#### Chapter Data

This format of the data contains the audiobook recording at the chapter-level. Each chapter-level waveform is accompanied by the text and its respective word-level alignment. Alignment was performed using the method described in [1].

Data per book:

| Data type                     | Description                                              |
| ----------------------------- | -------------------------------------------------------- |
| `./{book}/wav/{speaker}/.wav` | Waveforms for book chapters                              |
| `./{book}/txt/.txt`           | Text files with the corresponding text for book chapters |
| `./{book}/ctm/{speaker}*.ctm` | ctm text file with word-level alignment.                 |



#### Segmented Data

The chapter-level alignment was used to segment the data into utterances. This provides a more convenient way to use the data for Text-to-Speech synthesis or Voice Conversion. Waveforms are organized per speaker and, utterance ids are consistent within each book. If utterances are missing for a given speaker, it is implied that the alignment failed, so the utterance was excluded.

Some books are read jointly by multiple speakers (denoted *various* in the chapter-level data). For this reasons, some speakers may have a very small amount of data. Note that speaker names are consistent across the entire dataset, so a single speaker may read data from multiple books.

Data per book:

| Data type                      | Description                                                  |
| ------------------------------ | ------------------------------------------------------------ |
| `./{book}/wav/{speaker}/*.wav` | Waveforms following chpXX_uttXXX naming convention.          |
| `txt.punc`                     | original text without any processing other than sentence tokenization. |
| `txt.clean`                    | cleaned text stripped of punctuation and (very minor) text normalization |
| `spk2gender`                   | table mapping speakers to gender                             |
| `spk2utt`                      | table mapping speakers to a list of available utterances     |
| `utt2spk`                      | mapping utterances to a list of speakers                     |
| `spk2dur`                      | table mapping a speaker to amount of data in hours           |

Each waveform is a single-channel 16-bit PCM WAV sampled at 22050 Hz.
Note that these waveforms were original provided by LibriVox as MP3 files.



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
|                                 |             |

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

