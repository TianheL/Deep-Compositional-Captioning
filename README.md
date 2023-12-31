# Deep Compositional Captioning
A pytorch reproduction of "Deep Compositional Captioning: Describing Novel Object Categories without Paired Training Data". 

Origin Paper: <https://arxiv.org/abs/1511.05284>.
You can find the code of the author here <https://github.com/LisaAnne/DCC>. 
But it is implemented in caffe.

This is also the third project of NNDL course, which requires us to implement a novel image captioner on MSCOCO.

I just implement direct transfer since it is better than delta transfer according to the origin paper.

F1-Score of my reproduction:
| Model | bottle | bus | couch | microwave | pizza | racket | suitcase | zebra | Avg. |
| :---: | :----: | :-: | :---: | :-------: | :---: | :----: | :------: | :---: | :--: |
| DCC (paper) | 4.63 | 29.79 | 45.87 |   28.09   | 64.59 | 52.24 | 13.16 | 79.88 | 39.78 |
| DCC No Transfer (ours) | 0.00 | 0.00 | 0.00 | 0.00 | 0.00 | 0.00 | 0.00 | 0.00 | 0.00 |
| DCC Direct Transfer(ours) | 11.52 | 34.44 | 58.70 |   13.00   | 70.44 | 40.91 | 20.47 | 86.22 | 41.96 |

Metris on overall testset
| Model     | BLEU-1 | CIDEr  | METEOR | SPICE  | ROUGE-L |
|-----------|--------|--------|--------|--------|---------|
| DCC (paper)   | 64.4   | 59.1   | 21.00  | 13.4   | -       |
| DCC (ours)    | 62.2   | 52.5**   | * | 12.3   | 45.0    |

*: Cocoevalcap crashed when test meteor (I don't know why)

**: CIDEr score may have some problem, since I found that doubling the dataset with the same ground truth and generated captions result in a higher CIDEr.

Codes will be released soon...

