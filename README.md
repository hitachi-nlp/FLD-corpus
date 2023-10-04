# FLD Corpus
This repository includes the released FLD corpora.

See [the entry-point repository](https://github.com/hitachi-nlp/FLD.git) about the whole FLD project.

## About this release
This is version 2.0 of FLD corpora. See [the arXiv version of our paper](https://arxiv.org/abs/2308.0733) for details.

## The released corpora

### (recommended) Loading the corpora via 🤗 huggingface hub
You can load the corpora simply as follows:
1. First, install the huggingface datasets library:
```console
$ pip install datasets
```

2. Then, load the corpora from python scripts as:
```python
from datasets import load_dataset
FLD = load_dataset('hitachi-nlp/FLD.v2', name='default')
FLD_star = load_dataset('hitachi-nlp/FLD.v2', name='star')
(...)
```

Currently, we have released two corpora:
* [**FLD** (FLD.3)](https://huggingface.co/datasets/hitachi-nlp/FLD.v2/viewer/default/train), which includes lower depth proof trees.
* [**FLD★**(FLD.4) ](https://huggingface.co/datasets/hitachi-nlp/FLD.v2/viewer/star/train), which includes higher depth proof trees.

### Download the source files
Alternatively, you can manually download [the source files](https://drive.google.com/file/d/1BcI8lp3ye6vxOoRmcd_ORawytWQnH2yO/view?usp=sharing).

## Deduction examples
A deduction example in our corpora is conceptually as depicted in the following figure:

![deduction_example](./images/deduction_example.PNG)

For how to use the corpora for language model training, refer to [the language model based prover](https://github.com/hitachi-nlp/FLD-prover.git).
