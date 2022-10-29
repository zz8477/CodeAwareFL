### This is the online repository of Code-Aware Fault Localization with Reverse Diagnosis based on Interpretable Machine Learning.
## Task Definition

A code-aware fault localization technique with reverse diagnosis based on interpretable machine learning.

## Dataset

The experimental study chooses 12 widely used subject programs to conduct comparable studies and get a reliable result. Among them, chart, math, lang, and time are collected from [Defects4j](http://defects4j.org);
python, gzip and libtiff are got from [ManyBugs](http://repairbenchmarks.cs.umass.edu/ManyBugs/);
space and the four separate releases of nanoxml are acquired from [SIR](http://sir.unl.edu/portal/index.php).

### Data Format

1. dataset/data.jsonl is stored in jsonlines format. Each line in the uncompressed file represents one code snippet of space obtained by executing test cases and conducting dynamic slicing.

2. train.txt, valid.txt and vul_test.txt provide the needed data, stored in the following format:    **idx	label**

## Dependency

- python version: python3.7.6
- pip install torch
- pip install transformers
- sudo apt install build-essential
- pip install tree_sitter
- pip install sklearn


## Fault localization

```shell
cd CodeAwareFL
cd dataset
unzip dataset.zip
cd ..
python localize.py dev
```
### Get the result
We provide the result ranking list in txt form, 5718 is the faulty location.
```shell
cd CodeAwareFL
cd saved_models
vim predictions.txt
```


## Result

Ranking list on the test set are shown as below:
| Method      |   top-1   |   top-3   |   top-5   |    MFR    |    MAR    |
| ----------- | :-------: | :-------: | :-------: | :-------: | :-------: |
| CodeAwareFL |   5.26%   |   23.54%  |   32.43%  |    42     |    61     |
