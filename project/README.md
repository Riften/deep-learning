# A Small project using HOURGLASS-NETWORKS
A model trained by hourglass networks. See details at here: http://www-personal.umich.edu/~alnewell/pose/

The train and validation data can be download from here:https://pan.baidu.com/s/1o8dimWq  
Once you have downloaded these data, please put them in a file renamed as "dataset". And put that file in where the code is.
These data is shared by Chenxi Wang. I would like to thank him for his contribution of data processing here. I have to see that the most difficult part of using this model is how to solve the dataset.    

The processing detail of data is here:  

1)	The model can only be used to estimate the pose of a single person. So I have to select the images that have people with their annotations from the data set.  
2)	There are different kinds of objects in the image. So the annotation of people’s pose may be mixed with the annotation of other objects. So I need to select the annotation of people’s pose from all of the annotation. Fortunately, all of the annotation is labeled by different classification.  
3)	Their might be more than one people in the image, while the data set can only solve single person pose estimation. So I need to choose the right object that the model will work on. And remove other annotation. I check the center of different people and select the one closest to the center of the image.  
4)	The size of image is note suitable for the model. I transport it simply by resize and crop the images. I make it by using the crop function in the model. And the annotation of these objects should obtain the same conversion.  
5)	Then the processed data should be fed into the model. That was the most complex process. I have thought about making some h5 files just like the original model. But it seems a little difficult. Finally, with the help from Wang, I using the functions in the model to get the data directly. That means using the data extracted from the dataset to create some tensors and use them directly.  

However, as the training process is really time consuming, I have only train a simple model with 20 times training on the training data. As the training time is too small, this model can only get 50% accuracy on the validation data. I will train it again later to get a higher accuracy. Besides, as the trained model is too large to be uploaded to github, I will try another way to upload it.

