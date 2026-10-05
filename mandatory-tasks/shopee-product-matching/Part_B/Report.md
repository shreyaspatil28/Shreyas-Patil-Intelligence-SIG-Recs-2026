## Experiment Table

| Experiment   | Representation | Similarity | Threshold | F1 Score |
| ------------ | -------------- | ---------- | --------- | -----    |
| Baseline     | TF-IDF         | Cosine     | 0.5       | 0.4294   |
| Experiment 1 | ...            | ...        | ...       | ...   |
| Experiment 2 | ...            | ...        | ...       | ...   |
---

The baseline of TF-IDF predicts purely based on titles of the labels. It converts the labels into a TF-IDF vector where TF-IDF is calculated by TF(t, d) x IDF (t, D). Then choosing a threshold we consider products having cosine similarity of TF-IDF vectors greater than threshold to be same product label. TF-IDF is a good pick for this problem as it gives importance to frequently occurring words and also rare words so products having same rare words have a high chance that they are under same product label and are not left out.
F1 Score is the harmonic mean of Precision and Recall. Precision is true positives by all predicted positives, Recall is true positives by all actual positives. Thus if we increase threshold, some true positives are missed out which decreases precision and if we decrease threshold, some negatives are reported as positives which increases FN and hence decreases Recall, both which decrease the F1 Score. Thus an optimum threshold must be chosen.

---

Cases where model predicts same but actually isn't

Suppose `iPhone 12 Case` and `iPhone 12 Cover`, their cosine similarity is high but they are not same products as case and cover are not same. So model performs poor on products having similar names but differing in few words and are different products.

Actual example from dataset : `mainan bayi gantung putar musik merry go round` and `Merry Go Round PS317 - Mainan Bayi Gantung Putar`

Cases where model predicts different but actually is same

When one product is a generic name of the item and the other is a specific item but same product, model can't see this as they will have low cosine similarity for eg `16gb RAM Laptop` and `HP Victus Ryzen 7`.

Actual example from dataset : `LVN COLLAGEN - ORIGINAL TERMURAH - LVN STROBERI - GARANSI UANG KEMBALI` and `LVN Collagen / Stroberi eco 1box (10 sachet)`

---


