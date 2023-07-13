# FLD Corpus
This is one of the official repositories of the paper [Learning Deductive Reasoning from Synthetic Corpus based on Formal Logic](TODO).
This repository includes the released corpora.  

See [the entry-point repository](https://github.com/hitachi-nlp/FLD.git) for the other repositories used in the paper.

## About this release
* This is version 2.0 of FLD corpora with improved natural language template quality, logical proof consistency, and harder distractors. These corpora are slightly different from those used in the paper.

## Corpora
Download from [Here](TODO).

## Prover performance
A prover trained for 20000 steps on each corpus will perform as follows:

| corpus           | extr_stps.D-all.proof_accuracy | strct.D-all.answer_accuracy | D-all.answer_accuracy |
|------------------|--------------------------------|-----------------------------|-----------------------|
| FLD.3 (**FLD**)  | 86.4                           | 72.8                        | 94.6                  |
| FLD.4 (**FLD★**) | 60.4                           | 38.0                        | 73.2                  |

See [the prover repository](https://github.com/hitachi-nlp/FLD-prover.git) for more details.

## Citation
```bibtex
@inproceedings{morishita2023FLD,
  title={Learning Deductive Reasoning from Synthetic Corpus based on Formal Logic},
  author={Morishita, Terufumi and Morio, Gaku and Yamaguchi, Atsuki and Sogawa, Yasuhiro},
  booktitle={International Conference on Machine Learning},
  year={2023},
  organization={PMLR}
}
```
