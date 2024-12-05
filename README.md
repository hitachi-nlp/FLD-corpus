# FLD Corpus
This repository includes the released FLD corpora.

See [the entry-point repository](https://github.com/hitachi-nlp/FLD.git) about the whole FLD project.

## Available Corpora
* **(NEW!)** NeurIPS(2024): [**FLDx2** (Formal Logic Deduction Diverse)](https://huggingface.co/datasets/hitachi-nlp/FLDx2), which is the most diverse version of the FLD corpora.
* LREC-COLING (2024): The Japanese corpora, or **JFLD**, described [here](./README.JFLD.md).
* ICML(2023): The first FLD corpora (of version 2.0, described in the Appendix.H):
    * [**FLD** (FLD.3)](https://huggingface.co/datasets/hitachi-nlp/FLD.v2/viewer/default/train)
    * [**FLD★**(FLD.4) ](https://huggingface.co/datasets/hitachi-nlp/FLD.v2/viewer/star/train)

## How to use the corpora
First, install the datasets library:
```console
pip install datasets
```

Then, you can load the FLD corpora as follows:
```python
from datasets import load_dataset
FLD = load_dataset('hitachi-nlp/FLDx2', name='default')
```

## What does the dataset example look like?

### Concept
An example of deduction example in our dataset is conceptually illustrated in the figure below:

![deduction_example](./images/deduction_example_GPT4.png)

That is, given a set of facts and a hypothesis, a model must generate a proof sequence and determine an answer marker (proved, disproved, or unknown).

### Schema

The most important fields are:
* `context` (or `facts` in the later version of corpora): A set of facts.
* `hypothesis`: A hypothesis.
* `proofs`: Gold proofs. Each proof consists of a series of logical steps derived from the facts leading towards the hypothesis. Currently, for each example, we have at most one proof.
* `world_assump_label`: An answer, which is either `PROVED`, `DISPROVED`, or `UNKNOWN`.

To train an LLM:
* Use `prompt_serial` for the prompt, which is the serialized representation of the facts and the hypothesis.
* Use `proof_serial` for the output to be generated, which is the serialized representation of the proof and answer.
    - Note that, for the FLDx2 corpus, `proof_serial` sometimes includes both the proof and answer, and sometimes only the answer, working as a sort of augmentation.

For more about the training, see [the training repository](https://github.com/hitachi-nlp/FLD-prover).

The actual schema can be viewed on [the huggingface hub](https://huggingface.co/datasets/hitachi-nlp/FLDx2).
