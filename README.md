# ToxicSpansDetection

In the field of Natural Language Processing, the detection of text toxicity has become a significant challenge. To facilitate the research in this sphere, one of the tasks of the International Workshop on Semantic Evaluation 2021 is Toxic Spans Detection. The essential objective of this task is to identify toxic spans within English passages. In this paper, two approaches for toxic spans detection considered: Machine Reading Comprehension and modified Named Entity Recognition approach altogether with Machine Reading Comprehension, but also these approaches are improved by Question Generation method. Furthermore, this research presents the exploratory analysis of provided data, proposes a training process and examines the analysis of the results on F1-score of new state-of-the-art BERT-based Language Models: BERT, ALBERT, RoBERTa, XLM-RoBERTa and SpanBERT. Finally, the best language model obtained an F1-score of 0.688 on the test data.


In Analytics file you can find meme :)
| Name     | Character |
| ---      | ---       |
| Backtick | `         |




|                                   |   MRC NO FINE-TUNED |   MRC SQUAD |   MRC SQUAD + QG |   MRC+NER NO GQ |   MRC+NER QG |   Усредненные результаты по моделям |
|:-----------------------------------|--------------------:|------------:|-----------------:|----------------:|-------------:|------------------------------------:| |BERT                                |              0.489  |      0.471  |           0.48   |          0.652  |       0.763  |                             0.571  | |ALBERT                              |              0.546  |      0.515  |           0.534  |          0.64   |       0.731  |                             0.5932 |  |SpanBERT                            |              0.483  |      0.477  |           0.464  |          0.652  |       0.746  |                             0.5644 | |XLM-RoBERTa                         |              0.569  |      0.537  |           0.515  |          0.533  |       0.715  |                             0.5738 | |RoBERTa                             |              0.365  |      0.347  |           0.4    |          0.577  |       0.756  |                             0.489  | |Усредненные результаты по подходам |              0.4904 |      0.4694 |           0.4786 |          0.6108 |       0.7422 |                            0.55828 |
