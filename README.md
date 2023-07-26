# Car Recommendations on the basis of Visual Similarity

Recommend user cars to user on the basis of their visual likeness. 

## Dataset 

Uses [Stanford Cars Dataset](https://www.kaggle.com/datasets/jessicali9530/stanford-cars-dataset?select=cars_train)
The `cars_data_upload_to_drive.ipynb` file lets you initialize the data and metadata labels for the images and downloads it onto your google drive via colab, this is done to have a seamless interface between the data since normal colab procedures made you re-download and unzip the dataset everytime your runtime would reset which felt annoying if you worked for long hours on the project , hence uploading it to your google drive seems to be the best solution for both problems.

The training and testing data has been reduced to sub-folders in the `car_recommender_model.ipynb` file to reduce similarity computation time drastically and makes it easier to generate similar results for any image of choice from the whole 16000 image dataset.

## Model 
Model architecture is using the ResNet18 model to compute image features. 
Implemented a ResNet model from scratch with pre-trained weights as the original architecture provides more accurate images due to its pre-trained weights this is done to reduce time for computation and preserve accuracy instead of training it from scratch on a dataset, since the resnet model is already used professionally and it had the best results and after numerous amounts of testing, I decided to settle ResNet18 for my image feature extractor as it had the fastest compute time.

## Recommendation Generation
Given a target car, extract its visual features using the resnet model, calculate the visual similarity between the target image and training image subsets using cosine similarity from scikit-learn.
Retrieves the top-N cars with the highest visual similarity scores.
The outputs have a high cosine similarity value most of the times (in the range of 0.70 to 0.94) and the images visually look similar in the end which was difficult to achieve with my own resnet implementation 

## Possible Improvements 
> To use text labels as encodings for generating better recommendations and not limiting it to visual features only

## Conclusions 
In retrospect, there's a lot more things i wanted to do with this project like exploring nlp techniques and encorporating RNNs to have a proper recommender system used in professional environments but this was definitely a step in the right direction since I got the opportunity to learn about computer vision techniques in detail.
