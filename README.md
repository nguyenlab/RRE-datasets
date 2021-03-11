# RRE-datasets

This repo contains datasets for the task of Recognizing Requisite-Effectuation structures in legal texts.

# Data format

## japan-pension dataset

- Tagging scheme: IOE
- Text encoding: `Shift JIS`
- File format: `tsv`
- Columns: Head word [TAB] Function word [TAB] Punctuation (if any) [TAB] Label

Example:

`給付は、その支給をすべき事由が生じたときは、その事由が生じた日のする月の翌月からその事由がした日のする月の分の支給をする。`
```tsv
給付	は	、	E-S2
その	その	NO	I-R
支給	を	NO	I-R
す	べき	NO	I-R
事由	が	NO	I-R
生じ	た	NO	I-R
とき	は	、	E-R
その	その	NO	I-E
事由	が	NO	I-E
生じ	た	NO	I-E
日	の	NO	I-E
する	する	NO	I-E
月	の	NO	I-E
翌月	から	NO	I-E
その	その	NO	I-E
事由	が	NO	I-E
し	た	NO	I-E
日	の	NO	I-E
する	する	NO	I-E
月	の	NO	I-E
分	の	NO	I-E
支給	を	NO	I-E
する	する	。	E-E
```



# Experimental Results

## japan-pension dataset

 Method    |  F1 (%)
-----------|------
[Nguyen et al., 2018](https://doi.org/10.1007/s10506-018-9225-1) | 93.77 
[bert-base-multilingual-cased](https://huggingface.co/bert-base-multilingual-cased) (max len: 128) | 91.60
[bert-base-multilingual-cased](https://huggingface.co/bert-base-multilingual-cased) (max len: 256) | 91.46
[Kyoto bert-base](https://github.com/yoheikikuta/bert-japanese) (max len: 128)  | 90.01
[Kyoto bert-base](https://github.com/yoheikikuta/bert-japanese) (max len: 256)  | 89.89
[Tohoku bert](https://huggingface.co/cl-tohoku/bert-base-japanese) (max len: 256)   | 90.93
[Tohoku bert char](https://huggingface.co/cl-tohoku/bert-base-japanese-char) (max len: 256)   | 91.36
[Tohoku bert wwm](https://huggingface.co/cl-tohoku/bert-base-japanese-whole-word-masking) (max len: 256) | 90.66
[Tohoku bert cwwm](https://huggingface.co/cl-tohoku/bert-base-japanese-char-whole-word-masking) (max len: 256) | 89.40
[Cinamon electra small discriminator](https://huggingface.co/Cinnamon/electra-small-japanese-discriminator) (max len: 256) | 85.80
[Cinamon electra small generator](https://huggingface.co/Cinnamon/electra-small-japanese-generator) (max len: 256) | 88.57
[Albert JA v2](https://huggingface.co/ALINEAR/albert-japanese-v2) (max len: 256) | 90.09




 

# Citation
Please cite the following paper when using the datasets.

```bib
@article{10.1007/s10506-018-9225-1,
author = {Nguyen, Truong-Son and Nguyen, Le-Minh and Tojo, Satoshi and Satoh, Ken and Shimazu, Akira},
title = {Recurrent Neural Network-Based Models for Recognizing Requisite and Effectuation Parts in Legal Texts},
year = {2018},
issue_date = {June      2018},
publisher = {Kluwer Academic Publishers},
address = {USA},
volume = {26},
number = {2},
issn = {0924-8463},
url = {https://doi.org/10.1007/s10506-018-9225-1},
doi = {10.1007/s10506-018-9225-1},
journal = {Artif. Intell. Law},
month = jun,
pages = {169–199},
numpages = {31},
keywords = {Sequence labeling, Legal text analysis, Recognizing requisite and effectuation parts, Deep learning, Long short-term memory, Recurrent neural networks, Conditional random fields}
}

```
