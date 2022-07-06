# Vietnamese Multi-hop Question Answering (VIMQA) Dataset

## Introduction

VIMQA, a new Vietnamese dataset with over 10,000 Wikipedia-based multi-hop question-answer pairs. The dataset is
human-generated and has four main features:

1. The questions require advanced reasoning over multiple paragraphs.

2. Sentence-level supporting facts are provided, enabling the QA model to reason and explain the answer.

3. The dataset offers various types of reasoning to test the model's ability to reason and extract relevant proof.

4. The dataset is in Vietnamese, a low-resource language

The dataset is created using the [VIMQA-Maker](https://github.com/vimqa/vimqa-maker) tool.

## Dataset Overview

- Total examples: 10,047
- Train: 8,041
- Dev: 1,003
- Test: 1,003

## Dataset Format

Similar to [HotpotQA](https://hotpotqa.github.io/)

The top level structure of each JSON file is a list, where each entry represents a question-answer data point. Each data
point is a dict with the following keys:

- `_id`: a unique id for this question-answer data point. This is useful for evaluation.
- `question`: a string.
- `answer`: a string. The test set does not have this key.
- `supporting_facts`: a list. Each entry in the list is a list with two elements `[title, sent_id]`, where `title`
  denotes the title of the paragraph, and `sent_id` denotes the supporting fact's id (0-based) in this paragraph. The
  test set does not have this key.
- `context`: a list. Each entry is a paragraph, which is represented as a list with two elements `[title, sentences]`
  and `sentences` is a list of strings.

## Dataset Demo Examples

You can view the dataset demo examples at the [examples](dataset_examples) folder. The folder contains 10 examples for each train, dev, and test split.

## How to get the full dataset
To download the full dataset, you have to sign the [User Agreement form](VIMQA_EULA.pdf) and send it to the dataset owner (the email of the owner is in the form).

You will receive instructions to download the full dataset after you sign and send the User Agreement form.

## Citation
If you use our dataset, please cite the following paper.
```
@InProceedings{le-EtAl:2022:LREC,
  author    = {Le, Khang  and  Nguyen, Hien  and  Le Thanh, Tung  and  Nguyen, Minh},
  title     = {VIMQA: A Vietnamese Dataset for Advanced Reasoning and Explainable Multi-hop Question Answering},
  booktitle      = {Proceedings of the Language Resources and Evaluation Conference},
  month          = {June},
  year           = {2022},
  address        = {Marseille, France},
  publisher      = {European Language Resources Association},
  pages     = {6521--6529},
  abstract  = {Vietnamese is the native language of over 98 million people in the world. However, existing Vietnamese Question Answering (QA) datasets do not explore the model's ability to perform advanced reasoning and provide evidence to explain the answer. We introduce VIMQA, a new Vietnamese dataset with over 10,000 Wikipedia-based multi-hop question-answer pairs. The dataset is human-generated and has four main features: (1) The questions require advanced reasoning over multiple paragraphs. (2) Sentence-level supporting facts are provided, enabling the QA model to reason and explain the answer. (3) The dataset offers various types of reasoning to test the model's ability to reason and extract relevant proof. (4) The dataset is in Vietnamese, a low-resource language. We also conduct experiments on our dataset using state-of-the-art Multilingual single-hop and multi-hop QA methods. The results suggest that our dataset is challenging for existing methods, and there is room for improvement in Vietnamese QA systems. In addition, we propose a general process for data creation and publish a framework for creating multilingual multi-hop QA datasets. The dataset and framework are publicly available to encourage further research in Vietnamese QA systems.},
  url       = {https://aclanthology.org/2022.lrec-1.700}
}
```
