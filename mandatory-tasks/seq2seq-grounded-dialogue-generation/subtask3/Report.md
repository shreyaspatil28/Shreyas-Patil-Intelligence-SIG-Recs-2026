The task requires us to combine the power of two encoders to generate Hinglish text. This is done by a dialogue encoder and a document encoder.
The dialogue encoder contains hidden and cell states of information of the conversational context while the document encoder has factual information
from the wikipedia file provided.
Now the hidden and cell states from both decoders are used to generate text. The hidden state from dialogue encoder is fed to the decoder as conversation is 
decided by context and the document is accessed through attention while generating response.

Luong Attention is used here also and on both encoders. The hinglish vocabulary is tokenised from scratch and trained using Bucket Batch sampling where 
we create batches of train sentences of similar lengths to avoid excessive padding. Training shows that both training loss and val loss decrease so 
model is learning and not overfitting but the generated responses are very poor and out of context and alaso very generic. The model has not picked up
patterns from the small 8k rows dataset quite well so I think even training the model for 20-30 epochs would make the model good. The BLEU score is 
terribly low and also responses generated for large sentences are also small. Mostly due to Greedy Decoding the generic responses are generated.
