# Hallucinations-C2T :chart_with_upwards_trend:

Code for the paper "Tackling Hallucinations in Neural Chart Summarization" (Presented at INLG 2023).


Training and inference code is adapted from huggingface T5 [documentation](https://huggingface.co/docs/transformers/model_doc/t5). 

## Datasets Utilized in the Paper
Contains chart summarization data from two sources

1) [Chart2text (c2t-small)](https://github.com/JasonObeid/Chart2Text)
2) [Chart-to-text (c2t-big)](https://github.com/vis-nlp/Chart-to-text (statista data))

## To reproduce the results on google colab, kindly see the table below: 

Kindly use the data splits in `data` folder. 

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


## Citation 
```
@inproceedings{obaid-ul-islam-etal-2023-tackling,
    title = "Tackling Hallucinations in Neural Chart Summarization",
    author = "Obaid ul Islam, Saad  and
      {\v{S}}krjanec, Iza  and
      Dusek, Ondrej  and
      Demberg, Vera",
    editor = "Keet, C. Maria  and
      Lee, Hung-Yi  and
      Zarrie{\ss}, Sina",
    booktitle = "Proceedings of the 16th International Natural Language Generation Conference",
    month = sep,
    year = "2023",
    address = "Prague, Czechia",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2023.inlg-main.30",
    doi = "10.18653/v1/2023.inlg-main.30",
    pages = "414--423",
    abstract = "Hallucinations in text generation occur when the system produces text that is not grounded in the input. In this work, we tackle the problem of hallucinations in neural chart summarization. Our analysis shows that the target side of chart summarization training datasets often contains additional information, leading to hallucinations. We propose a natural language inference (NLI) based method to preprocess the training data and show through human evaluation that our method significantly reduces hallucinations. We also found that shortening long-distance dependencies in the input sequence and adding chart-related information like title and legends improves the overall performance.",
}
```
