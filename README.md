# g2pW: Mandarin Grapheme-to-Phoneme Converter

[![Downloads](https://pepy.tech/badge/g2pw)](https://pepy.tech/project/g2pw)[![license](https://img.shields.io/badge/license-Apache%202.0-red)](https://github.com/GitYCC/g2pW/blob/master/LICENSE)

**Authors:** [Yi-Chang Chen](https://github.com/GitYCC), Yu-Chuan Chang, Yen-Cheng Chang and Yi-Ren Yeh

This is the official repository of our paper [g2pW: A Conditional Weighted Softmax BERT for Polyphone Disambiguation in Mandarin](https://arxiv.org/abs/2203.10430).

## Getting Started

### Dependency / Install

(This work was tested with PyTorch 1.7.0, CUDA 10.1, python 3.6 and Ubuntu 16.04.)

- Install [PyTorch](https://pytorch.org/get-started/locally/)

- `$ pip install g2pw`



### Quick Demo

```python
>>> from g2pw import G2PWConverter
>>> conv = G2PWConverter()
>>> sentence = '上校請技術人員校正FN儀器'
>>> conv(sentence)
[['ㄕㄤ4', 'ㄒㄧㄠ4', 'ㄑㄧㄥ3', 'ㄐㄧ4', 'ㄕㄨ4', 'ㄖㄣ2', 'ㄩㄢ2', 'ㄐㄧㄠ4', 'ㄓㄥ4', None, None, 'ㄧ2', 'ㄑㄧ4']]
>>> sentences = ['銀行', '行動']
>>> conv(sentences)
[['ㄧㄣ2', 'ㄏㄤ2'], ['ㄒㄧㄥ2', 'ㄉㄨㄥ4']]
```


### Use GPU to Speed Up

```python
conv = G2PWConverter(use_cuda=True)
```


### Support Simplified Chinese and Pinyin

```
$ pip install g2pw[opencc]
```

```python
>>> from g2pw import G2PWConverter
>>> conv = G2PWConverter(style='pinyin', enable_non_tradional_chinese=True)
>>> conv('然而，他红了20年以后，他竟退出了大家的视线。')
[['ran2', 'er2', None, 'ta1', 'hong2', 'le5', None, None, 'nian2', 'yi3', 'hou4', None, 'ta1', 'jing4', 'tui4', 'chu1', 'le5', 'da4', 'jia1', 'de5', 'shi4', 'xian4', None]]
```

## Citation

```
@misc{chen2022g2pw,
      title={g2pW: A Conditional Weighted Softmax BERT for Polyphone Disambiguation in Mandarin}, 
      author={Yi-Chang Chen and Yu-Chuan Chang and Yen-Cheng Chang and Yi-Ren Yeh},
      year={2022},
      eprint={2203.10430},
      archivePrefix={arXiv},
      primaryClass={cs.CL}
}
```
