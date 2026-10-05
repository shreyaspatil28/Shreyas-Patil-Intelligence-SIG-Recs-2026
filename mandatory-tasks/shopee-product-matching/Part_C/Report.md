For image based product matching I used a pre-trained ResNet18 model which is a CNN model which has 18 layers in its architecture. 
It has convolutional layers followed by batch normalisation and ReLU and also solves the vanishing gradients problem by including a shortcut 
path for gradients to flow.

The images are trained and preprocessed which includes resizing the image to fit ResNet18 input size, converting PIL image to tensor and the 
pixel values being normalized and fed to the pretrained model.

Images are also then embedded into numbers using the feature maps and trained using cosine similarity to find highly similar images and match
them as same product group, check against actual value and backpropagate gradients. 

The F1 Score obtained was 0.39 which shows purely image based matching is less efficient than title based matching
