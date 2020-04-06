# Natural Perturbations for BoolQ 
This repository contains the resources relevant to the following publication:

```bibtex 
@article{khashabi2020naturalperturbations,
  title={Natural Perturbation for Robust Question Answering},
  author={D. Khashabi and T. Khot and A. Sabhwaral},
  journal={arXiv preprint},
  year={2020}
}
```

The data here BoolQ-NQ is an extension to BoolQ, a dataset that was originally released in [Clark et al, 2019](https://github.com/google-research-datasets/boolean-questions).


The dataset is organzied as a `.jsonl` file, i.e. each line is a json. Here is an example: 
```json
{"cluster-id": "25938", "question_id": "267", "is_seed_question": 0, "split": "train", "passage": "(Thanksgiving (United States)) Thanksgiving, or Thanksgiving Day, is a public holiday celebrated on the fourth Thursday of November in the United States. It originated as a harvest festival. Thanksgiving has been celebrated nationally on and off since 1789, after Congress requested a proclamation by George Washington. It has been celebrated as a federal holiday every year since 1863, when, during the American Civil War, President Abraham Lincoln proclaimed a national day of ``Thanksgiving and Praise to our beneficent Father who dwelleth in the Heavens,'' to be celebrated on the last Thursday in November. Together with Christmas and the New Year, Thanksgiving is a part of the broader fall/winter holiday season in the U.S.", "question": "is thanksgiving sometimes the last thursday of the month?", "hard_label": "True", "soft_label": 0.75, "roberta_hard": true, "ind_human_label": "?"}
```


Here the keys are: 
 - The question and its relevant passgae are defined with the `question` and `passage` fields. 
 - The gold yes/no gold answer is defined with the `hard_label` field. I have also included a "soft" label in `soft_label` in you wanna know how many have agreed on this label. 
 - The dataset split is indicated with `split`. 
 - `roberta_hard` indicates whether it was a difficult question for a RoBERTa trained on BoolQ. 
 - `ind_human_label` additional human label elicited for the instances included in the `test` split. 
 - `is_seed_question` indicates whether this question is borrowed from the original BoolQ dataset. 
- `cluster-id`: one thing to notice about the data is that it comes as clusters of questions. The questions that belong to the same cluster share the same `cluster-id`. 


Here are some statistics on the data:

| Measure                 | Full  | Train | Dev  | Test |
|-------------------------|-------|-------|------|------|
| \# of questions         | 17323 | 9727  | 4434 | 3162 |
| \# of ``yes'' questions | 9724  | 5733  | 2263 | 1728 |
| \# of ``no'' questions  | 7599  | 3994  | 2171 | 1434 |
| \# of clusters          | 4064  | 2408  | 919  | 737  |
| average cluster size    | 4.3   | 4.1   | 4.8  | 4.3  |
| median cluster size     | 3.0   | 3.0   | 3.0  | 3.0  |
