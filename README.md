# Hallucinations-C2T

Code for the paper "Tackling Hallucinations in Neural Chart Summarization" (Presented in INLG 2023).


Training and inference code is adapted from huggingface T5 [documentation](https://huggingface.co/docs/transformers/model_doc/t5). 

## Data
Contains chart summarization data from two sources

1) [Chart2text (c2t-small)](https://github.com/JasonObeid/Chart2Text)
2) [Chart-to-text (c2t-big)](https://github.com/vis-nlp/Chart-to-text (statista data))

## To reproduce the results, kindly see the table below: 

| **Model Version**                                | **Model Repository**                             |
|--------------------------------------------------|--------------------------------------------------|
| Pre-trained T5-base                              | [https://huggingface.co/t5-base](https://huggingface.co/t5-base) |
| **Parameter**                                    | **Value**                                        |
| Maximum input length                             | 1024                                             |
| Maximum target length                            | 512                                              |
| Truncation                                       | True                                             |
| Padding                                          | max_length                                       |
| batch size                                       | 2                                                |
| Optimizer                                        | Weighted Adam                                    |
| Learning rate                                    | 3e-4                                             |
| Weight decay                                     | 0.01                                             |
| Training epochs and hours for T5-S-O&HL          | 6 epochs, 11 hours                               |
| Training epochs and hours for T5-S-OL            | 6 epochs, 11 hours                               |
| Training epochs and hours for T5-AC-orig         | 8 epochs, 6 hours                                |
| Training epochs and hours for T5-AC-noisy        | 8 epochs, 6 hours                                |
| Training epochs for T5-S-OL-NLI                  | 6 epochs, 11 hours                               |
| Training epochs for T5-B-OL                      | 12 epochs, 37 hours                              |
| Training runs for all the models                 | Single run                                       |
| Beam size                                        | 4                                                |
| GPU                                              | Tesla T4 16 GB                                   |



