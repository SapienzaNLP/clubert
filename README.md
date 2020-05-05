# CluBERT
This repository contains data for [CluBERT: A Cluster-Based Approach forLearning Sense Distributions in Multiple Languages](https://www.researchgate.net/publication/341151563_CluBERT_A_Cluster-Based_Approach_for_Learning_Sense_Distributions_in_Multiple_Languages)
ACL paper.

CluBERT is a multilingual approach for automatically producing distribution of senses from a corpus of raw text.
We use [BabelNet](babelnet.org) as inventory of meanings that is shared across languages.
# Data
Within the package clubert_v0.9.tar.gz you will find the sense distributions for all the lexemes
tagged within English, Italian, Spanish, French and German Senseval and SemEval competitions for Word Sense Disambiguation
(Senseval-2, Senseval-3, SemEval2007 task 17, SemEval2013 task 12, SemEval 2015 task 13).
Please refer to the [WSD English Evaluation Framework](http://lcl.uniroma1.it/wsdeval/evaluation-data) for the test sets
in English and to the latest release of multilingual WSD tasks of SemEval2013 and SemEval2015
made available by Sapienza NLP group at https://github.com/SapienzaNLP/mwsd-datasets.

**Soon we will release the distributions for all lemmas in the WordNet part of BabelNet.**

The package is structured as follows:
```bash
clubert_v0.9
├── answers
│   ├── de
│   │   └── semeval2013-de.answers.txt
│   ├── en                                                                                                                                            [0/1954]
│   │   ├── ALL.answers.txt
│   │   ├── semeval2007.answers.txt
│   │   ├── semeval2013.answers.txt
│   │   ├── semeval2015.answers.txt
│   │   ├── senseval2.answers.txt
│   │   └── senseval3.answers.txt
│   ├── es
│   │   ├── semeval2013-es.answers.txt
│   │   └── semeval2015-es.answers.txt
│   ├── fr
│   │   └── semeval2013-fr.answers.txt
│   └── it
│       ├── semeval2013-it.answers.txt
│       └── semeval2015-it.answers.txt
├── de
│   ├── lexemes_distributions.bnid.txt
│   └── lexemes_distributions.wnid.txt
├── en
│   ├── lexemes_distributions.bnid.txt
│   ├── lexemes_distributions.wnid.txt
│   └── lexemes_distributions.wnkey.txt
├── es
│   ├── lexemes_distributions.bnid.txt
│   └── lexemes_distributions.wnid.txt
├── fr
│   ├── lexemes_distributions.bnid.txt
│   └── lexemes_distributions.wnid.txt
└── it
    ├── lexemes_distributions.bnid.txt
    └── lexemes_distributions.wnid.txt
```
For each language, we provide a text file containing rows structured as follows:
`lemma#POS[TAB]sense_1:score_1[TAB]sense_2:score_2[TAB] ... [TAB]sense_n:score_n`
and `[TAB]` is the tab character `\t`.
The `bnid` files represent senses as BabelNet synset ids whilst `wnid` as WordNet synset offsets (WordNet version 3.0).
As for English, we also provide a `wnkey` file representing senses with WordNet sense keys.

The folder `answers` contains the answers for the gold standard datasets' instances. 
We divided the answers by language and provide an `answer` file for each dataset. We note that if the system was not able
to provide an answer for a given dataset instance, that instance will be missing in the answer file. This is required by
the scorer released in the English WSD Evaluation framework to properly compute Precision, Recall and F1. 
Please refer to http://lcl.uniroma1.it/wsdeval/evaluation-data for the English evaluation datasets and to https://github.com/SapienzaNLP/mwsd-datasets
for the multilingual evaluation datasets (WordNet split (wn) of the latest version (0.1.6)).  
# Reference
When using the data in this repository, please reference the following paper.
```
@inproceedings{pasini-etal-2020-clubert,
    title = {{CluBERT: A Cluster-Based Approach for Learning Sense Distributions in Multiple Languages}},
    author = {Pasini, Tommaso and Scozzafava, Federico, and Scarlini, Bianca},
    booktitle = {Proceedings of the 58th Annual Meeting of the Association for Computational Linguistics},
    year = {2020},
    publisher = {Association for Computational Linguistics}
}

```
# License
All data and codes provided in this repository are subject to the  Attribution-Non Commercial-ShareAlike 4.0 International license (CC BY-NC 4.0).

[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)
