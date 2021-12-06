# Dog-Breed-Classifier

this repository for the Udacity ML Nanodegree project Dog breed classifier.

## Project Overview :

The project's purpose is to create a machine learning model that can be integrated into a web app to process real-world, user-supplied photos. Two tasks must be completed by the algorithm:

- The algorithm will determine a dog's breed based on a photograph of the canine.
- If a human photograph is provided, the code will identify the dog breed that most closely resembles it.
Convolutional Neural Networks can be used to handle the challenge of multiclass classification.
There are three steps to the solution. 
- To begin, we can leverage existing algorithms such as OpenCV's implementation of Haar feature-based cascade classifiers to detect human images. 
- Second, we'll utilise a VGG16 model that has been pre-trained to recognise dog photos. 
- Finally, after determining whether the image is dog or human, we can send it to a CNN model, which will analyse it and suggest the breed that best matches the image out of 133 breeds.

## CNN model built from the ground up

- To overcome the problem, I created a CNN model from the ground up. There are three convolutional layers in the model. 
- Kernel size 3 and stride 1 are used in all convolutional layers. 
- The 224*224 input picture is used by the first conv layer (conv1), and the final conv layer (conv3) creates a 128 output size. 
- Here, the ReLU activation function is used. 
- The pooling layer (2,2) is used, resulting in a 2x reduction in input size. 
- two layers that are totally coupled and provide a 133-dimensional output. 
- To avoid overfitting, a 0.25 dropout is included.

## Refinement - Using transfer learning, a CNN model was developed.

- CNN developed from scratch has a 31 percent accuracy, the model can be greatly improved by using transfer learning. 
- To develop a CNN using transfer learning, I chose the Resnet101 architecture, which is 101 layers deep and pre-trained on the ImageNet dataset. 
- Our model uses Resnet101's last convolutional output as an input. 
- To get a 133-dimensional output, we merely need to add a completely connected layer (one for each dog category). 
- When compared to CNN created from scratch, the model performed exceptionally well. The model had an accuracy of 76 percent after only 6 epochs.

## Evaluation of the Model

- The CNN model was trained for 6 epochs using transfer learning and ResNet101 architecture, 
- and the final model had an accuracy of 81 percent on test data.  
- the algorithm correctly predicted 5085 of 6680.
