## Contents

There are four audiobooks books in this dataset.

| Identifier | Book                                                     |
| ---------- | -------------------------------------------------------- |
| emma       | Emma, by Jane Austen                                     |
| huck       | The Adventures of Huckleberry Finn, by Mark Twain        |
| sherlock   | The Adventures of Sherlock Holmes, by Arthur Conan Doyle |
| treasure   | Treasure Island, by Robert Louis Stevenson               |

The data is provided in two formats: at the chapter and at the utterance-level.

Each book is read by multiple speakers. Waveforms are single-channel 16-bit PCM WAVs sampled at 22050 Hz. Note that the waveforms were original provided by LibriVox as MP3 files.



#### Chapter Data

This format of the data contains the audiobook recording at the chapter-level. Each chapter-level waveform is accompanied by the text and its respective word-level alignment. Alignment was performed using the methods described in [[1]](https://msamribeiro.github.io/parallel-corpus/#references).

Data per book:

| Data type                     | Description                                              |
| ----------------------------- | -------------------------------------------------------- |
| `./{book}/wav/{speaker}/.wav` | Waveforms for book chapters                              |
| `./{book}/txt/.txt`           | Text files with the corresponding text for book chapters |
| `./{book}/ctm/{speaker}*.ctm` | ctm text file with word-level alignment.                 |



#### Segmented Data

The chapter-level alignment was used to segment the data into utterances. This provides a more convenient way to use the data for Text-to-Speech synthesis or Voice Conversion. Waveforms are organized per speaker and utterance ids are consistent within each book. If utterances are missing for a given speaker, it is implied that the alignment failed, so the utterance was excluded.

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



