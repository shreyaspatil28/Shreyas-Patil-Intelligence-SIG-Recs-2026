## Experiment Table

| Experiment   | Representation | Similarity | Threshold | F1 Score |
| ------------ | -------------- | ---------- | --------- | -----    |
| Baseline     | TF-IDF         | Cosine     | 0.5       | 0.4294   |
| Experiment 1 | ...            | ...        | ...       | ...   |
| Experiment 2 | ...            | ...        | ...       | ...   |
---

The baseline of TF-IDF predicts purely based on titles of the labels. It converts the labels into a TF-IDF vector where TF-IDF is calculated by TF(t, d) x IDF (t, D). Then choosing a threshold we consider products having cosine similarity of TF-IDF vectors greater than threshold to be same product label.
F1 Score is the harmonic mean of Precision and Recall. Precision is true positives by all predicted positives, Recall is true positives by all actual positives. Thus if we increase threshold, some true positives are missed out which decreases precision and if we decrease threshold, some negatives are reported as positives which increases FN and hence decreases Recall, both which decrease the F1 Score. Thus an optimum threshold must be chosen.
---
Cases where model predicts same but actually isn't

