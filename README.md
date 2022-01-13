# Eye-For-Blind

In this capstone project, we created a deep learning model which can explain the contents of an image in the form of speech through caption generation with an attention mechanism on Flickr8K dataset. This kind of model is a use-case for blind people so that they can understand any image with the help of speech. The caption generated through a CNN-RNN model will be converted to speech using a text to speech library.

Kaggle Link: https://www.kaggle.com/adityajn105/flickr8k
### Summary

- In this project, we firstly read the image and captions file. Once proper cleaning and conversion to proper shape and size of images and captions done, we extracted the feature of images using InceptionV3 model.
- After that we build the Encoder, Attention and Decoder Model using TensorFlow sub classing method.
- Encoder Model- To bring the image features to embedding dim shape and apply proper activation for smooth processing.
- Attention Model- We used the attention model to make our decoder focus on a particular part of the image at a time instead of focusing on the entire image.
- Decoder(RNN here- GRU)- The decoder returned the predicted caption and the decoder's hidden state as output, which was sent back to the model and the predictions were used to calculate the loss using cross-entropy "SparseCategoricalCrossentropy".We also used teacher forcing to decide the next input to the decoder.The decoder stopped predicting once the end token was predicted by the model.
- We used greedy search method to calculate the probability of the words according to their occurrence in the vocabulary. It takes the sample of the words and then outputs/predicts the word with the highest probability.
- Finally, we used "BLEU score" as the evaluation metric for the predicted word. It measured the similarity of the predicted caption and the real caption.
