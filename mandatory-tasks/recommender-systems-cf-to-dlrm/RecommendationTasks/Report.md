Collaborative Filtering learns relationships from users and items and predicts that users who interacted with a particular item may interact with this item  

DLRM is better suited for CTR predictions as it converts the numerical features into dense vectors passed through the bottom mlp and each of the categorical features
get their own embedding table then the dlrm calculates pairwise interaction of every dense vector and embedded categorical vector  
This quantitatively gives meaningful interactions between objects and the model learns given these users, items and interactions what is the probability of a click??  

A vanilla neural network also uses embeddings but it specially doesn't use embeddings for each categorical feature and does not use pairwise interactions like the DLRM
However, in this case this architectural difference of DLRM did not convert into better results than the vanilla neural network which might be happening 
because there is sparse data to point out the meaningful interactions between features and users to predict clicks
