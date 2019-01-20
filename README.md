# NeuralMachineTranslation
Experiments with Seq2Seq and Transformer models and English to German translation.

This repository contains experiments with two machine translation models in pytorch. The first one is a sequence-to-sequence model with multi-head attention and the second model is a transformer as implemented in tensorflow.

The goal of the experiments is to see how the models compare in performance, how well they can be trained etc.

The English to German dataset used comes from: <a href='http://www.manythings.org/'>http://www.manythings.org/</a> and has been cleaned and saved as TSV file. The set contains 169,197 sentences.

Both model have been run for 30 epochs. WER was used as scoring function (blue : seq2seq, red : transformer):
 
![Alt text](valid_scores.png?raw=true "")

Note, that both models have been trained in a similar fashion (no warm-up for the transformer) and use the same techniques for multi-head attention, label smoothing loss, token to word encoding, and scoring.

<i>Seq2Seq with Multi-head Attention Model:</i>

  Greedy Decoding<br>
  CPU times: user 11.9 s, sys: 77.5 ms, total: 12 s<br>
  Test Summary:   Bleu: 41.110, WER:  35.228, CER:  33.395 ,ACC:  17.702

  Beam Search Decoding (beam width 20)<br>
  CPU times: user 7min 48s, sys: 619 ms, total: 7min 49s <br>
  Test Summary:  Bleu: 38.210, WER:  37.487, CER:  35.314, ACC:  17.135

<i>Transformer Model:</i>

  Greedy Decoding<br>
  CPU times: user 43.2 s, sys: 217 ms, total: 43.4 s<br>
  Test Summary:  Bleu: 43.570, WER:  35.392, CER:  33.750, ACC:  19.818<br>

  Beam Search Decoding (beam width 20)<br>
  CPU times: user 7min 48s, sys: 619 ms, total: 7min 49s <br>
  Test Summary:  Bleu: 44.060 WER:  32.789 CER:  35.598 ACC:  29.774<br>
