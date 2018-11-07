The Parallel Audiobook Corpus was mainly prepared for speech synthesis and voice conversion.

Audiobook recordings are a rich data source for **speech synthesis**. This corpus contains roughly 6-9 hours of speech data for individual speakers, with more data being available if pooled across books. The parallel corpus might be especially relevant for **prosody** modelling. Multiple readings of the same textual source can be useful to compare  prosodic variation of the same text across speakers. Additionally, speakers simulate character voices differently, which might lead to acoustic properties being emphasised differently across speakers.

For **voice conversion**, parallel data is essential for robust acoustic models. The segmented version of this data is conveniently prepared for this scenario. Matching utterance IDs across multiple speakers will result in a large parallel corpus for average voice models. See `utt2spk` for readings across speakers.

There are, of course, other applications. Feel free to use the data according to your interests. I would be happy to hear about the various scenarios you might use this data for.

