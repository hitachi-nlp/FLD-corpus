# FLD Corpus
This is the repository for FLD corpus.

## Introduction
FLD (**F**ormal **L**ogic **D**eduction) is synthetic a corpus for teaching language models deductive reasoning.
FLD corpus includes synthetically generated multistep deductive proofs written in natural languages.
Each deductive proof (dis)proves a hypothesis by applying deduction rules multiple times to a given set of facts.

## Data Format
FLD instance is composed of a hypothesis, a set of facts ("context"), possible proofs ("proofs"), an answer label ("answer"), and other meta properties, as follows:
```json
{
  "hypothesis": "it is not the fact that, the sloucher is nativist",
  "context": "sent1: a sloucher touting EHF causes a ranch that is a Oniscus sent10: for everything, if it is not the fact that, it touts EHF, it is not the fact that, it is a contagion sent11: if it is not the fact that something is hand-held, it is not the fact that, it scuffles saskatoon sent12: the sloucher is millennial sent13: a ranch not touting EHF is caused by a tappet that is not a Oniscus sent14: everything is a contagion sent15: if a ranch is nativist it collapses sent16: if a sloucher books it is nativist sent17: a sloucher is a Oniscus if it tilts sent18: the sloucher is a contagion sent19: the endonuclease touts EHF sent2: if it is not the fact that the sloucher blazes creepy-crawly, it is not the fact that the ranch is a contagion sent3: the ranch is a Oniscus, thus the sloucher books sent4: a ranch will not shelter cone thus it is not the fact that it eyes nosepiece sent5: a anticholinesterase is not nativist if it is not the fact that it is a Rochambeau sent6: a strongroom is oleaceous thus it touts EHF sent7: if the ranch is Swiss, the sloucher is a contagion sent8: a sloucher touts EHF if it is a contagion sent9: a PIE will not tout EHF thus it is not the fact that it poaches",
  "proofs": [
    "sent8 & sent18 -> int1: the sloucher touts EHF; sent1 & sent3 -> int2: a sloucher books if it touts EHF; int1 & int2 -> int3: the sloucher books; int3 & sent16 -> hypothesis;"
  ],
  "answer": false,

  "original_tree_depth": 3,
  "depth": 3,
  "num_formula_distractors": 14,
  "num_translation_distractors": 0,
  "num_all_distractors": 14
  "proof_stance": "DISPROOF",

  "negative_hypothesis": null,
  "negative_proofs": [],
  "negative_proof_stance": null,
  "negative_answer": null,
}
```

This format is similar to the one used in a [previous study](https://github.com/princeton-nlp/NLProofS).

## Current Release
Datasets can be found [here](https://drive.google.com/file/d/1qa-9c0skuZ_DvqqAM1uHQW-WzGinPCsv/view?usp=sharing), and their specs are as follows:

| corpus name | proof tree depth distribution | arguments (deduction rules) | proof tree depth | dataset size (train/valid/test) |
|-------------|-------------------------------|-----------------------------|------------------|---------------------------------|
| sFLD-impl   |             skewed            | implication                 | $1\sim3$         | 30k / 1k / 1k                   |
| sFLD-crit   |             skewed            | critical thinking           | $1\sim1$         | 30k / 1k / 1k                   |
| sFLD-axiom  |             skewed            | the axioms                  | $1\sim3$         | 30k / 1k / 1k                   |
| FLD.D5      | uniform                       | the axioms                  | $1\sim5$         | 30k / 1k / 1k                   |
| FLD-impl    | uniform                       | implication                 | $1\sim3$         | 30k / 1k / 1k                   |
| **FLD**     | uniform                       | the axioms                  | $1\sim3$         | 30k / 1k / 1k                   |
| **FLD★**    | uniform                       | the axioms                  | $1\sim8$         | 30k / 1k / 1k                   |

See the paper for other details.  


In the future, we will release various corpora which differ in design aspects, such as the number of distractors, the abundancy of linguistic templates, and the complexity of logical formulas.
These corpora will enable us investigate what aspects are important for acquring robust deductive reasoning ability.
