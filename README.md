# Hallucinations-C2T :chart_with_upwards_trend:

Code for the paper "[Tackling Hallucinations in Neural Chart Summarization](https://aclanthology.org/2023.inlg-main.30/)" presented at INLG 2023.

Training and inference code are adapted from Hugging Face T5 [documentation](https://huggingface.co/docs/transformers/model_doc/t5).

## Introduction

The trained model for investigations and state-of-the-art (SOTA) improvements are detailed in the paper: [Tackling Hallucinations in Neural Chart Summarization](https://aclanthology.org/2023.inlg-main.30/).

### Abstract

Hallucinations in text generation occur when the system produces text that is not grounded in the input. In this work, we address the problem of hallucinations in neural chart summarization. Our analysis reveals that the target side of chart summarization training datasets often contains additional information, leading to hallucinations. We propose a natural language inference (NLI) based method to preprocess the training data and demonstrate through human evaluation that our approach significantly reduces hallucinations. Additionally, we found that shortening long-distance dependencies in the input sequence and adding chart-related information such as titles and legends enhances overall performance.

## Main Findings from the Paper

- **Enhanced Context Provision:** Emphasizing the importance of providing more context and reducing long-distance dependencies in the input format.
- **NLI Cleaning Step:** Introducing an NLI-based cleaning step to eliminate ungrounded information in the training data.
- **Reduction of Intrinsic Hallucinations:** Demonstrating that reducing long-distance dependencies and adding more context leads to fewer intrinsic hallucinations.
- **Cause of Extrinsic Hallucinations:** Identifying that extrinsic hallucinations are caused by ungrounded information in training summaries.
- **Human Evaluation Results:** Showing that using NLI to filter training summaries significantly reduces hallucinations.

## Datasets Utilized in the Paper

This project utilizes chart summarization data from the following sources:

### Chart-to-Text / Chart2Text
- [GitHub Repository](https://github.com/vis-nlp/Chart-to-text)
- [GitHub Repository](https://github.com/JasonObeid/Chart2Text)
- [Processed Hugging Face Dataset](https://huggingface.co/datasets/saadob12/chart-to-text)


### Autochart
- [GitLab Repository](https://gitlab.com/bottle_shop/snlg/chart/autochart)
- [Processed Hugging Face Dataset](https://huggingface.co/datasets/saadob12/Autochart)

## Reproducing Results on Google Colab

To reproduce the results, please use the data splits located in the `data` folder.

### Model Versions and Repositories

| **Model Version**    | **Model Repository**                                     |
|----------------------|----------------------------------------------------------|
| Pre-trained T5-base  | [t5-base](https://huggingface.co/t5-base)                |

### Training Parameters

| **Parameter**                       | **Value**          |
|-------------------------------------|--------------------|
| Maximum input length                | 1024               |
| Maximum target length               | 512                |
| Truncation                          | True               |
| Padding                             | `max_length`       |
| Batch size                          | 2                  |
| Optimizer                           | Weighted Adam      |
| Learning rate                       | 3e-4               |
| Weight decay                        | 0.01               |
| Beam size                           | 4                  |
| GPU                                 | Tesla T4 16 GB     |

### Training Epochs and Duration

| **Model Configuration**          | **Epochs** | **Training Time** |
|----------------------------------|------------|--------------------|
| T5-S-O & HL                      | 6          | 11 hours           |
| T5-S-OL                          | 6          | 11 hours           |
| T5-AC-orig                       | 8          | 6 hours            |
| T5-AC-noisy                      | 8          | 6 hours            |
| T5-S-OL-NLI                      | 6          | 11 hours           |
| T5-B-OL                          | 12         | 37 hours           |
| All Models (Training Runs)       | Single run |                    |

## Citation

Please cite our work as follows:

```bibtex
@inproceedings{obaid-ul-islam-etal-2023-tackling,
    title = {Tackling Hallucinations in Neural Chart Summarization},
    author = {Obaid ul Islam, Saad and {\v{S}}krjanec, Iza and Dusek, Ondrej and Demberg, Vera},
    editor = {Keet, C. Maria and Lee, Hung-Yi and Zarrie{\ss}, Sina},
    booktitle = {Proceedings of the 16th International Natural Language Generation Conference},
    month = sep,
    year = {2023},
    address = {Prague, Czechia},
    publisher = {Association for Computational Linguistics},
    url = {https://aclanthology.org/2023.inlg-main.30},
    doi = {10.18653/v1/2023.inlg-main.30},
    pages = {414--423},
    abstract = {Hallucinations in text generation occur when the system produces text that is not grounded in the input. In this work, we tackle the problem of hallucinations in neural chart summarization. Our analysis shows that the target side of chart summarization training datasets often contains additional information, leading to hallucinations. We propose a natural language inference (NLI) based method to preprocess the training data and show through human evaluation that our method significantly reduces hallucinations. We also found that shortening long-distance dependencies in the input sequence and adding chart-related information like title and legends improves the overall performance.}
}
