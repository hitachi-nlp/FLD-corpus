# FLD Corpus
This repository includes the released FLD corpora.

See [the entry-point repository](https://github.com/hitachi-nlp/FLD.git) about the whole FLD project.

## About this release
* This is version 2.0 of FLD corpora. See the [the arXiv version](https://arxiv.org/abs/2308.0733) of our paper for details.

## The released corpora

### Using corpora via huggingface hub
The corpora are released on 🤗 the huggingface hub, so you can load a FLD corpus simply by:
```python
from datasets import load_dataset
FLD = load_dataset('FLD.v2')
(...)
```

Currently, we have released two corpora:
* [**FLD** (FLD.3)](https://huggingface.co/datasets/hitachi-nlp/FLD.v2), which includes lower depth proof trees.
* [**FLD★**(FLD.4) ](https://huggingface.co/datasets/hitachi-nlp/FLD-star.v2), which includes higher depth proof trees.

For how to use the corpora for language model training, refer to [the language model based prover](https://github.com/hitachi-nlp/FLD-prover.git).

### Download the source files
Alternatively, you can manually download [the source files](https://drive.google.com/file/d/1BcI8lp3ye6vxOoRmcd_ORawytWQnH2yO/view?usp=sharing).

## Deduction examples
A deduction example in our corpora is conceptually as depicted in the following figure:

![deduction_example](./images/deduction_example.PNG)

For how to use such examples for training language models, see [the prover repository](https://github.com/hitachi-nlp/FLD-prover/).
