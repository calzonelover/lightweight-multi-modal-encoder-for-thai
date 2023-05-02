# Lightweight Multi-modal Encoder for Thai
[[model]]() [[dataset]](https://huggingface.co/datasets/patomp/thai-mscoco-2014-captions)

This repository contains the model scripts of lightweight Thai text encoder using [thai2fit](https://github.com/cstorm125/thai2fit) [1] with the trained projection matrices. In addition, it also contains the processing script that translate image-caption pairs from english to thai.

## Dataset Construction

The dataset contructed from translating the captions of [MS COCO 2014 dataset](https://huggingface.co/datasets/HuggingFaceM4/COCO) [2] to Thai by using [NMT](https://airesearch.in.th/releases/machine-translation-models/) provided by VISTEC-depa Thailand Artificial Intelligence Research Institute [3]. The translated of 3 splits (train, validation and test) dataset was published in the [Huggingface](https://huggingface.co/datasets/patomp/thai-mscoco-2014-captions).

| Model \ Metrics | text-find-image recall@1  | text-find-image recall@10 | image-find-text recall@1  | image-find-text recall@10  |
| :---  | --- | --- | --- | --- |
| **Multilingual Encoder** | |   |   |   |
| [clip-ViT-B-32-multilingual-v1](https://huggingface.co/sentence-transformers/clip-ViT-B-32-multilingual-v1) | 0.075 | 0.242 | 0.096 | 0.286 |
| [XLM-Roberta-Large-Vit-B-32](https://huggingface.co/M-CLIP/XLM-Roberta-Large-Vit-B-32) | **0.226** | **0.565** | **0.265** | **0.596** |
| **Thai Encoder**   |  |  |   |  |
| [Thai-Cross-CLIP](https://github.com/vikimark/Thai-Cross-CLIP) | 0.167 | 0.475 | 0.197  | 0.523  |
| [Thiswork]() |   |     |   |   |


## Benchmark
For testing the cross-modal retrieval performance in Thai fot both directions: text-find-image and image-find-text. The results from  multilingual and dedicated Thai encoder are shown in the following table.

## References
[1] C. Polpanumas and W. Phatthiyaphaibun, thai2fit: Thai language Implementation of ULMFit. Zenodo, 2021. doi: 10.5281/zenodo.4429691. 

[2] Tsung-Yi Lin, Michael Maire, Serge Belongie, James Hays, Pietro Perona, Deva Ramanan, Piotr Dollár, and C. Lawrence Zitnick. 2014. Microsoft COCO: Common Objects in Context. In Computer Vision – ECCV 2014, Springer International Publishing, Cham, 740–755. 

[3] English-Thai Machine Translation Models. (2020, June 23).  VISTEC-depa Thailand Artificial Intelligence Research Institute. https://airesearch.in.th/releases/machine-translation-models/
