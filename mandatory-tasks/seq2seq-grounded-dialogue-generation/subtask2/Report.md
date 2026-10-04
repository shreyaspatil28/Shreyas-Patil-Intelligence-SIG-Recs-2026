Luong Attention is a game changer for this Seq2Seq Translaton. Baseline feeds the last hidden and cell states from the encoder to the decoder but with 
attention we feed the hidden and cell state at different timestamps so that the model instead of squeezing whole sentence into a context vector can now
track scores at each token and decide whether the word is important or can be forgotten.

The score is given as a product of the decoder's hidden state, the weight matrix and the encoder's hidden state for luong attention. Then the context vector
is the sum of product of all normalized scores and hidden states which changes according to time. Greedy Decoding is used as in the sentence with the 
highest probability is picked and once moved forward cannot look back on other combinations of sentences. Thus, Beam Search allows us to keep top K 
probable sentences at each time frame and select the highest probable sentence at the end.

Overall the attention model performs way better than baseline model with BLEU scores touching 30+ for short sentences and even 20+ for longer sentences.
There is also visible decrease in loss better than baseline model during training
