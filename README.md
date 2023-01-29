# JBLiMP: Japanese Benchmark of Linguistic Minimal Pairs

JBLiMP is a novel dataset for targeted syntactic evaluations of language models in Japanese. JBLiMP consists of 331 minimal pairs, which are created based on acceptability judgments extracted from journal articles in theoretical linguistics. These minimal pairs are grouped into 11 categories, each covering a different linguistic phenomenon. 

We evaluated the syntactic knowledge of several language models on JBLiMP: GPT-2, LSTM, and _n_-gram language models trained by (Kuribayashi et al, 2021). All the models achieved comparative accuracy around 75% and human baseline accuracy was 90.90%.

## Contents
- 
- 

## Data Format
|Name|Description|
|----|-----|
|ID|Ids of minimal pairs|
|year|Publication years of source articles|
|author|Authors of source articles|
|{good, bad}_num|Example numbers in source articles|
|{good, bad}_diacritic|Acceptability judgements in source articles|
|{good, bad}_sentence_raw|Raw example sentences in source articles (there are some fragmented sentences)|
|{good, bad}_sentence|Example sentences in JBLiMP (fragmented sentences are augumented)|
|{good, bad}_gloss|Glosses in source articles|
|{good, bad}_translation|English translations in source articles|
|type|Categorization based on the type of acceptability judgements and how those sentences were presented in source articles|
|phenomenon|Categorization based on linguistic phenomena|
|phenomenon-2|Categorization based on linguistic phenomena|
|paradigm|Sub-categorization of phenomenon|


# Recommended Citation
```
Taiga Someya and Yohei Oseki. 2023. JBLiMP: Japanese Benchmark of Linguistic Minimal Pairs. In Proceedings of the 17th Conference of the European Chapter of the Association for Computational Linguistics: Main Volume, pages ??-??, Dubrovnik, Croatia. Association for Computational Linguistics.
```

