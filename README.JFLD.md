# Japanese Formal Logic Deduction Corpus

## Available Corpora
語彙が異なる３種類のコーパスをリリースします．
語彙とは，論理記号へ割り当てられる語句群のことです．
論理の本質は語彙には依存しないので(*)，どのコーパスを使って貰っても問題無いと思います(実際，コーパス間で有意な性能差はありません)．
おそらく人間にとって一番分かりやすいであろう`JFLD_BCCWJ`をおすすめします．


* [JFLD](https://huggingface.co/datasets/hitachi-nlp/JFLD)
    - 語彙として，mecab辞書に含まれる全ての語句を使っています．
    - 言語処理学会の予稿で使われたコーパスです．
* [JFLD_BCCWJ](https://huggingface.co/datasets/hitachi-nlp/JFLD_BCCWJ)
    - `JFLD`の語彙には古風な単語・人名などが含まれているので，人間にとって，少々読みづらいです．
    - そこで，`JFLD_BCCWJ`では，語彙として現代的な語句(BCCWJの高頻度語句)を用いました．
* [JFLD_punipuni_monster](https://huggingface.co/datasets/hitachi-nlp/JFLD_punipuni_monster)
    - 語彙として...

(*)... 実は，LLMのような帰納的な機械の学習・評価を念頭に置くと，「語彙の違いは本質的ではございません」と切り捨てられない事情も出てきます．もし本当に語彙が本質的では無いのなら，そもそも語彙の割り当てなどせずに，論理式のままのコーパスでこと足りると思いますよね．しかし，LLMは(あまり大胆に帰納しない)帰納的な機械なので，例えば論理式のコーパスで学習すると，論理式で書かれた論理推論タスクは解けるが，日本語で書かれた論理推論タスクは解けない，ということが起こりえます．詳しくは，予稿のAppendix.2を参照してください．

## Citation
```bibtex
@article{morishita_2024_NLP_JFLD,
  title={日本語論理推論ベンチマークJFLDの提案},
  author={森下皓文 and 山口篤季 and 森尾学 and 角掛正弥 and 友成光 and 今一修, and 十河泰弘},
  journal={言語処理学会 第30年次大会 発表論文集},
  abbr={言語処理学会},
  year={2024}
}
```
