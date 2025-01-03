# causal-fallacies

EMNLP 2024 paper [LLMs Are Prone to Fallacies in Causal Inference](https://arxiv.org/abs/2406.12158)

### Data

The ```data/``` directory contains the following files:

1. ```synthetic_vertices100_40k.csv```: Synthetic data created from a ground truth causal graph with 100 nodes. The data contains a total of 40,000 scenarios (each on new line), where each scenario contains description about a chain of events from the graph. The description may include one or more of temporal relations, spatial relations, and counterfactuals. For the experiments in paper where we only finetune one type of relations (e.g. temporal relations), we filter scenarios to only keep those relations.

2. ```test_xy_causal.csv```: This test data contains pairs of events which have an edge between them in the ground truth causal graph. This test set is used to evaluate two rules --- absence of causal relations from temporal relations (rule 1, sec 6.1) and presence of causal relations from positive counterfactuals (rule 3, sec 6.1).

3. ```test_xy_unrelated_spatial.csv```: This test data contains (subset of) pairs of events which are not causally related, while ensuring that the corresponding negative spatial relation has been included in the finetuning dataset. Thus this test data can be used for evaluating absence of causal relations from negative spatial relations (rule 2, sec 6.1).

4. ```test_xy_unrelated_counterfactual.csv```: This test data contains (subset of) pairs of events which are not causally related, while ensuring that the corresponding negative counterfactuals for each pair are included in the finetuning dataset. Thus this test data can be used for evaluating absence of causal relations from negative counterfactuals (rule 4, sec 6.1).

### Citation

You can cite our work as follows:

```
@inproceedings{joshi2024causalfallacies,
        author={Nitish Joshi, Abulhair Saparov, Yixin Wang and He He},
        title={{LLM}s Are Prone to Fallacies in Causal Inference},
        booktitle={EMNLP},
        year={2024}
}
```

