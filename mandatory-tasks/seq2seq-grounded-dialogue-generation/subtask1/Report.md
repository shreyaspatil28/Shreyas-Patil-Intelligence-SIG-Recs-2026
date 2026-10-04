Seq2Seq model takes an English sentence as an input and converts it into tokens and use embeddings. This is fed to encoder and this generates one hidden state
and one cell state using LSTM. This has gates which allow it decide which information to remember which is important and which to forget.
Each hidden and cell state generated are at the end added to create a context vector which is then fed to the decoder. The decoder reads french words word 
by word and its losses are calculated with predicted against actual during training.

Since sentences are of different lengths, we could pad zeros to make sentences of equal length and check but this would take up lot of memory (I did that first
it took like 10 mins per epoch 🥀🥀🥀 so ditched it), instead we can bucket batch similar length sentences into a single batch to prevent excessive padding.  
What was done to fasten training is dropping rare words, limiting vocabulary of words, taking sentences of decent sizes; and to reduce overfitting added 
Dropout 

The model got a BLEU score of 11 which is terrible so it doesn't perform well however the BLEU score is fair for sentences with less than 10 words so the 
model goes haywire for longer sentences
