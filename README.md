The Parallel Audiobook Corpus (version 1.0) is a collection of parallel readings of audiobooks. The corpus consists of approximately **121 hours of data across 4 books and 59 speakers**.

The data is provided in two formats. *Chapter* data contains the audiobook recording at the chapter level. Each chapter-level waveform is accompanied by the text and its respective word-level alignment. This format can be used if you are looking for a segmentation that does not correspond to utterance-level units. *Segmented* data provides a more traditional format for the corpus. The chapter-level alignment was segmented into utterances with waveforms organized by speaker. Note that, within each book, utterance identifiers are consistent across speakers, making it easy to find parallel data.

Audio data is extracted from [LibriVox](https://librivox.org) and textual data is taken from [Project Gutenberg](https://www.gutenberg.org).

------



## Table of Contents

1. [Applications](doc/applications.md)
2. [Corpus Contents](doc/contents.md)
3. [Data Overview](doc/data-overview.md)
4. [File Formats](doc/file-formats.md)
5. [Data Sources](doc/data-sources.md)
6. [Related Corpora](doc/related-corpora.md)
7. [License](#license)
8. [Citation](#citation)
9. [Download](#download)
10. [Acknowledgements](#acknowledgements)
11. [References](#references)

------

## License

This data is licensed under a Creative Commons Attribution 4.0 International License ([CC BY 4.0](https://creativecommons.org/licenses/by/4.0)). This licence applies to the alignment and segmentation of the speech and text data.

The underlying audio and text are licensed under their specific data source terms. Please refer to their [respective sources](doc/data-sources.md) for a full description of those terms.



## Citation

If you'd like to cite this work, please use the following format:
```
@misc{pacorpus18,
  author = {Ribeiro,  Manuel Sam},
  title = {Parallel Audiobook Corpus},
  publisher = {University of Edinburgh},
  howpublished = {[dataset]. University of Edinburgh. School of Informatics. \url{https://doi.org/10.7488/ds/2468}},
  doi = {10.7488/ds/2468},
  url = {https://datashare.is.ed.ac.uk/handle/10283/3217},
  year = {2018}
}

```


## Download

The data can be downloaded from the following page: http://dx.doi.org/10.7488/ds/2468



## Acknowledgements

Many thanks to [Peter Bell](http://homepages.inf.ed.ac.uk/pbell1/) (CSTR, University of Edinburgh), who kindly provided the chapter-level word alignments. I would also like to extend my gratitude to all the volunteers at Librivox and Gutenberg for dedicating their time to distribute this wide variety of data.

This work was supported by the EPSRC Healthcare Partnerships grant number EP/P02338X/1 (Ultrax2020).



## References

[1] Bell, Peter, and Steve Renals. (2015) "A system for automatic alignment of broadcast media captions using weighted finite-state transducers." In Automatic Speech Recognition and Understanding (ASRU), pp. 675-680, 2015. Available [here](http://www.cstr.ed.ac.uk/downloads/publications/2015/bell15_alignment.pdf)

[2] ITU-T Recommendation G.191 (2009). Software tools for speech and audio coding standardization. International Telecommunication Union. Available [here](https://www.itu.int/rec/T-REC-G.191/en)

[3] Speech signal processing toolkit. (SPTK). Available [here](http://sp-tk.sourceforge.net).