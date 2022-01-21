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
