# ToxicSpansDetection

In the field of Natural Language Processing, the detection of text toxicity has become a significant challenge. To facilitate the research in this sphere, one of the tasks of the International Workshop on Semantic Evaluation 2021 is Toxic Spans Detection. The essential objective of this task is to identify toxic spans within English passages. In this paper, two approaches for toxic spans detection considered: [Machine Reading Comprehension](https://arxiv.org/abs/1910.11476) and [modified Named Entity Recognition approach altogether with Machine Reading Comprehension](https://arxiv.org/abs/1909.13375), but also these approaches are improved by [Question Generation](https://www.aclweb.org/anthology/P19-1129/) method. Furthermore, this research presents the exploratory analysis of provided data, proposes a training process and examines the analysis of the results on F1-score of new state-of-the-art BERT-based Language Models: BERT, ALBERT, RoBERTa, XLM-RoBERTa and SpanBERT. Finally, the best language model obtained an F1-score of 0.688 on the test data.


In Analytics file you can find meme :)

Files:
1. Analytics - the filw with all graphics and results from trained model
2. MRC + NER - realized MRC + NER Approach
3. MRC - realized MRC Approach

Parameters in the following table:
* MRC NO FINE-TUNED - usual MRC
* MRC SQUAD - pretrained model on SQuAD v2.0 and train on usual data
* MRC SQUAD + QG - pretrained model on SQuAD v2.0 and train on usual data with QG approach
* MRC+NER NO GQ - usual MRC + NER
* MRC+NER QG - MRC + NER with QG approach 


Results on test data (Base models):

|                                    |   MRC NO FINE-TUNED |   MRC SQUAD |   MRC SQUAD + QG |   MRC+NER NO GQ |   MRC+NER QG |   avg on the model |
|:-----------------------------------|--------------------:|------------:|-----------------:|----------------:|-------------:|------------------------------------:|
| BERT                               |              0.612  |      0.617  |           0.61   |          0.613  |       0.641  |                             0.6186  |
| ALBERT                             |              0.682  |      0.659  |           0.657  |          0.624  |       0.593  |                             0.643   |
| SpanBERT                           |              0.624  |      0.62   |           0.607  |          0.631  |       0.644  |                             0.6252  |
| XLM-RoBERTa                        |              0.683  |      0.686  |           0.688  |          0.566  |       0.658  |                             0.6562  |
| RoBERTa                            |              0.475  |      0.492  |           0.542  |          0.622  |       0.647  |                             0.5556  |
| Avg on approach |              0.6152 |      0.6148 |           0.6208 |          0.6112 |       0.6366 |                             0.61972 |


Results on test data (Large models):
|                                    |   MRC NO FINE-TUNED |   MRC SQUAD |   MRC SQUAD + QG |   MRC+NER NO GQ |   MRC+NER QG |   avg on models |
|:-----------------------------------|--------------------:|------------:|-----------------:|----------------:|-------------:|------------------------------------:|
| XXLargeALBERT                      |            0.679    |    0.685    |         0.618    |        0.603    |     0.599    |                            0.6368   |
| BERT                               |            0.605    |    0.602    |         0.606    |        0.634    |     0.652    |                            0.6198   |
| ALBERT                             |            0.674    |    0.681    |         0.649    |        0.596    |     0.625    |                            0.645    |
| SpanBERT                           |            0.601    |    0.595    |         0.603    |        0.635    |     0.636    |                            0.614    |
| XLM-RoBERTa                        |            0.683    |    0.598    |         0.677    |        0.632    |     0.647    |                            0.6474   |
| RoBERTa                            |            0.474    |    0.473    |         0.416    |        0.638    |     0.654    |                            0.531    |
| XLargeALBERT                       |            0.593    |    0.666    |         0.613    |        0.591    |     0.607    |                            0.614    |
| avg on approach |            0.615571 |    0.614286 |         0.597429 |        0.618429 |     0.631429 |                            0.615429 |
