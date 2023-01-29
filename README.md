# JBLiMP: Japanese Benchmark of Linguistic Minimal Pairs

JBLiMP is a novel dataset for targeted syntactic evaluations of language models in Japanese. JBLiMP consists of 331 minimal pairs, which are created based on acceptability judgments extracted from journal articles in theoretical linguistics. These minimal pairs are grouped into 11 categories, each covering a different linguistic phenomenon.


## Contents
- Minimal pairs before human validation (367 pairs) can be found in `data/raw`.
- Minimal pairs after human validation (331 pairs) can be found in `data/validated`.
    - In order to validate the quality of minimal pairs in JBLiMP, we conducted an acceptability judgement experiment. For each minimal pair, if the annotation of JBLiMP and the majority vote of human annotations do not match, that minimal pair is removed from JBLiMP.
    - **These human-validated minimal pairs were used for the evaluation of our language models.**

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

## Model Evaluation
We evaluated the syntactic knowledge of several language models on JBLiMP: GPT-2, LSTM, and _n_-gram language models trained by (Kuribayashi et al, 2021). All the models achieved comparative accuracy around 76% and human baseline accuracy was 90.90%.

| Model | Overall | Argument Structure  | Verbal Agreement| Morphology | Nominal Structure | Ellipsis | Quantifiers | Binding | Island effects| Filer-gap| NPI Licensing | Control/Raising           |
|------------------------|--------------------------|-----------|--------|-------------------------|----------------|---------------------------|-------------------------|--------------------------|---------|-------|-------------------|-------------------|
| Trans-LG  | 77.95                    | 89.05     | 53.55  | 82.86                   | **95.65** | 85.96                     | 73.81                   | 58.97                    | 75.76   | 55.56 | 50.00             | <ins> 16.67</ins> |
| Trans-SM               | 76.54                    | 89.05     | 44.26  | 82.86                   | **97.10** | 89.47                     | 71.43                   | 46.15                    | 84.85   | 55.56 | 75.00             | <ins> 0.00</ins> |
| LSTM                   | 75.73                    | 86.67     | 46.99  | 83.81                   | **95.65** | 91.23                     | 66.67                   | <ins> 41.03</ins>        | 87.88   | 44.44 | 66.67             | 50.00             |
| 5-gram                 | 74.02                    | 78.57     | 57.38  | 82.86                   | 86.96          | **89.47**            | 78.57                   | 53.85                    | 72.73   | 66.67 | <ins> 50.00</ins> | 0.00              |
| Human                  | 90.90                    | 92.19     | 89.62  | 94.86                   | **97.68** | 87.37                     | 85.71                   | 82.05                    | 92.12   | 78.52 | 90.00             | <ins> 70.00</ins> |
| Model Ave.             | 76.06                    | 85.76     | 50.55  | 83.10                   | **93.84** | 89.03                     | 72.62                   | 50.00                    | 80.31   | 55.56 | 60.42             | <ins> 16.67</ins> |

Accuracy is averaged over 3 different random seeds except 5-gram and human. The numbers in bold indicate the best score within a model, while the number with underscore indicates the worst score

# Recommended Citation
```
Taiga Someya and Yohei Oseki. 2023. JBLiMP: Japanese Benchmark of Linguistic Minimal Pairs. In Proceedings of the 17th Conference of the European Chapter of the Association for Computational Linguistics: Main Volume, pages ??-??, Dubrovnik, Croatia. Association for Computational Linguistics.
```

