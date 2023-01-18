## Image Captioning
Providing description to an image using pertained Resnet-50 model trained on ImageNet dataset.

Image Captioning is the process of generating textual description of an image. It uses
both Natural Language Processing and Computer Vision to generate the captions. 
The idea is to design a model which will learn from an avaialbe dataset in the form [image → captions]. The dataset consists of input images and their corresponding output captions.

![Picture 1](https://user-images.githubusercontent.com/87992010/213118904-294a7503-b4c9-4ef2-9a9d-55a179912046.png)

#### **Encoder** -
The Convolutional Neural Network(CNN) can be thought of as an encoder. The input image is given to CNN to extract
the features. The last hidden state of the CNN is connected to the Decoder.
#### **Decoder** -
The Decoder is a Recurrent Neural Network(RNN) which does language modelling up to the word level. The first time
step receives the encoded output from the encoder and also the <START> vector.

#### **Below are the steps to achieve the desired captioning model using Resnet-50:**
1. Read the pickle file (https://drive.google.com/file/d/1A8g74ohdb_5d2fPjc72yF7GxufE9GRcu/view?usp=sharing) and
convert the data into the correct format which could be used for ML model.
Pickle file contains the image id and the text associated with the image.
Eg: '319847657_2c40e14113.jpg#0\tA girl in a purple shirt hold a pillow .
Each image can have multiple captions.
319847657_2c40e14113.jpg -> image name
#0 -> Caption ID
\t -> separator between Image name and Image Caption
A girl in a purple shirt hold a pillow . -> Image Caption
Corresponding image wrt image name can be found in the image dataset folder.
Image dataset Folder : https://drive.google.com/file/d/1-mPKMpphaKqtT26ZzbR5hCHGedkNyAf1/view?usp=sharing

2. Bring the train and test data in the required format.
3. Use Pretrained Resnet-50 model trained on ImageNet dataset (available publicly on google) for image feature extraction.
4. Create one layered LSTM layer model and other relevant layers for image caption generation.
5. Add L1 regularization to the LSTM layer.
6. Add one layer of dropout at the appropriate position.
7. Choose the appropriate activation function for all the layers.
8. Train the model for an appropriate number of epochs. Print the train and validation loss for each epoch. Use the appropriate
batch size.
9. Take a random image from google and generate caption for that image.
#### <i>"a man in a red shirt be play in a field" </i>
![baseball](https://user-images.githubusercontent.com/87992010/213120903-fe7c83ac-fde6-4da9-b606-ec57effc3c30.jpg)
