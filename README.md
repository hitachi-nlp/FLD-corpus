# FLD Corpus
This repository includes the released FLD corpora.

See [the entry-point repository](https://github.com/hitachi-nlp/FLD.git) about the whole FLD project.



## About this release
This is version 2.0 of FLD corpora. See [the arXiv version of our paper](https://arxiv.org/abs/2308.0733) for details.



## How to use the corpora

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




## What does the dataset example look like?

### Overview
An example of deduction in our dataset is conceptually illustrated in the figure below:

![deduction_example](./images/deduction_example.PNG)

That is, given a set of facts and a hypothesis, a model must generate a proof sequence and determine an answer marker (proved, disproved, or unknown).

### Schema
Our example contains several fields.

The most important ones include:
* `prompt_serial`: A serialization of facts and a hypothesis used as input for a language model.
* `proof_serial`: A serialization of the proof and answer marker used as output for a language model.

These fields can be used to train a causal language model.

For more details, refer to [the language model-based prover](https://github.com/hitachi-nlp/FLD-prover.git).
