# FLD Corpus
This repository includes the released FLD corpora.

See [the entry-point repository](https://github.com/hitachi-nlp/FLD.git) about the whole FLD project.


## About this release
This is version 2.0 of FLD corpora. See the Appendix.H of [our paper](https://arxiv.org/abs/2308.07336) for details.


## Installation
You need datasets library to load the corpora:
```console
$ pip install datasets
```

## How to use the corpora
We released two corpora via 🤗 huggingface hub as follows:
* [**FLD** (FLD.3)](https://huggingface.co/datasets/hitachi-nlp/FLD.v2/viewer/default/train), which includes lower depth proof trees.
* [**FLD★**(FLD.4) ](https://huggingface.co/datasets/hitachi-nlp/FLD.v2/viewer/star/train), which includes higher depth proof trees.

You can load these corpora as follows:
```python
from datasets import load_dataset
FLD = load_dataset('hitachi-nlp/FLD.v2', name='default')
FLD_star = load_dataset('hitachi-nlp/FLD.v2', name='star')
```

## What does the dataset example look like?

### Overview
An example of deduction in our dataset is conceptually illustrated in the figure below:

![deduction_example](./images/deduction_example_GPT4.png)

That is, given a set of facts and a hypothesis, a model must generate a proof sequence and determine an answer marker (proved, disproved, or unknown).

### Schema
The most primitive fields are:
* `context`: A set of facts.
* `hypothesis`: A hypothesis.
* `proofs`: Gold proofs. Each proof consists of a series of logical steps derived from the facts leading towards the hypothesis. Currently, for each example, we have at most one proof.
* `world_assump_label`: An answer, which is either `PROVED`, `DISPROVED`, or `UNKNOWN`.

Additionally, we have preprocessed fields as follows:
* `prompt_serial`: A serialized representation of the facts and the hypothesis.
* `proof_serial`: A serialized representation of the proof and answer.

To train or evaluate a Language Model (LM), one can take one of two approaches:
* Use `prompt_serial` as input and `proof_serial` as output. This will make the LM to generate both the proof and the answer.
* Use `prompt_serial` as input and `world_assump_label` as output. This will make the LM to generate only the answer.
