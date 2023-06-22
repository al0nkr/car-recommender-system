# Car Recommendations on the basis of Visual Similarity

Recommend user cars to user on the basis of their visual likeness. 

## Dataset 

Uses [Stanford Cars Dataset](https://www.kaggle.com/datasets/jessicali9530/stanford-cars-dataset?select=cars_train)

> task : load pre processed car images and the the text labels, convert text class labels to numerical values using [label encoding](https://www.geeksforgeeks.org/ml-label-encoding-of-datasets-in-python/)

## Model 
Model architecture combines both visual and text information, using a CNN model like ResNet or VGG for extracting visual features from the images and an Embedding layer followed by a RNN to capture textual information

>task : concatenate visual and text features to form a join representation tensor

## Recommendation Generation
Given a target car, extract its visual features using the pre-trained CNN model, calculate the visual similarity between the target car and other cars in the dataset using cosine similarity.
Retrieve the top-N cars with the highest visual similarity scores.
Additionally, consider the text classes of the top-N cars and recommend cars with similar text classes.

## UI 2ndary tasks
User friendly interface for users to interact with recommendation system : allows user to input target car , view recommended cars , filter recommendations based on text classes if need be.

>additional task : represent recommended data with labels and sort by features 
