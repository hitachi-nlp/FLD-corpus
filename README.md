# FLD Corpus
This is one of the official repositories of the paper [Learning Deductive Reasoning from Synthetic Corpus based on Formal Logic](https://proceedings.mlr.press/v202/morishita23a.html).
This repository includes the released corpora.  

See [the entry-point repository](https://github.com/hitachi-nlp/FLD.git) for the other repositories used in the paper.

## About this release
* This is version 2.0 of FLD corpora with improved natural language template quality, logical proof consistency, and harder distractors. These corpora are slightly different from those used in the paper.

## Corpora
Download from [Here](https://drive.google.com/file/d/16XpDBslr56Qdm41CqApI8MYtPky1swKU/view?usp=sharing).

## Prover performance
A prover trained for 20000 steps on each corpus will perform as follows:

| corpus           | extr_stps.D-all.proof_accuracy | strct.D-all.answer_accuracy | D-all.answer_accuracy |
|------------------|--------------------------------|-----------------------------|-----------------------|
| FLD.3 (**FLD**)  | 86.4                           | 72.8                        | 94.6                  |
| FLD.4 (**FLD★**) | 60.4                           | 38.0                        | 73.2                  |

See [the prover repository](https://github.com/hitachi-nlp/FLD-prover.git) for more details.

## Citation
```bibtex
@InProceedings{pmlr-v202-morishita23a,
  title = 	 {Learning Deductive Reasoning from Synthetic Corpus based on Formal Logic},
  author =       {Morishita, Terufumi and Morio, Gaku and Yamaguchi, Atsuki and Sogawa, Yasuhiro},
  booktitle = 	 {Proceedings of the 40th International Conference on Machine Learning},
  pages = 	 {25254--25274},
  year = 	 {2023},
  editor = 	 {Krause, Andreas and Brunskill, Emma and Cho, Kyunghyun and Engelhardt, Barbara and Sabato, Sivan and Scarlett, Jonathan},
  volume = 	 {202},
  series = 	 {Proceedings of Machine Learning Research},
  month = 	 {23--29 Jul},
  publisher =    {PMLR},
  pdf = 	 {https://proceedings.mlr.press/v202/morishita23a/morishita23a.pdf},
  url = 	 {https://proceedings.mlr.press/v202/morishita23a.html},
  abstract = 	 {We study a synthetic corpus based approach for language models (LMs) to acquire logical deductive reasoning ability. The previous studies generated deduction examples using specific sets of deduction rules. However, these rules were limited or otherwise arbitrary. This can limit the generalizability of acquired deductive reasoning ability. We rethink this and adopt a well-grounded set of deduction rules based on formal logic theory, which can derive any other deduction rules when combined in a multistep way. We empirically verify that LMs trained on the proposed corpora, which we name $\textbf{FLD}$ ($\textbf{F}$ormal $\textbf{L}$ogic $\textbf{D}$eduction), acquire more generalizable deductive reasoning ability. Furthermore, we identify the aspects of deductive reasoning ability on which deduction corpora can enhance LMs and those on which they cannot. Finally, on the basis of these results, we discuss the future directions for applying deduction corpora or other approaches for each aspect. We release the code, data, and models.}
}
```
