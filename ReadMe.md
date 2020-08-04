###### Problem statement:

The task is to visualize the given image for its missing part, rust etc. 
I am providing two solutions for the above problems( one for each).

## Dependencies:
1. Python 3.5+
2. Keras
3. Tensorflow
4. Numpy
5. Pandas
6. Matplotlib
7. OpenCV

###### For rust detection/phone crack detection etc. defects:

I prepared a model using transfer learning. I used VGG16 for this. I downloaded the weights(no top weights - https://www.kaggle.com/kmader/full-keras-pretrained-no-top) and loaded it. Added a convolution layer followed by final dense layer. 
Since there was no training data provided, I chose steel surface default detection dataset(https://www.kaggle.com/c/severstal-steel-defect-detection/data) to mask the area which has the defect. 
The model has train loss of 0.06.
I later loaded the weights of the model to predict the defect in other images. For instance I chose phone crack image to mask the region with defect(here crack).

###### For detection of missing part.

To solve this task, I chose one shot learning method where I prepared a siamese model to give the similarity score between different images.
In this way if any item is missing in the new image (which the old image had), based on the score, I can know if given two images are same or not.

I chose Omniglot dataset (https://github.com/brendenlake/omniglot/tree/master/python) since I couldnot find relevant hardware dataset.
I achieved one shot model accuracy of 78%.


