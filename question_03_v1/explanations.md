**Question 3a**. 
I have divided the dataset into training and test sets using the train_test_split function from the sklearn.model_selection module.

real_train, real_test = train_test_split(real_files, test_size=0.2, random_state=42)
fake_train, fake_test = train_test_split(fake_files, test_size=0.2, random_state=42)


First I separated the file names of real and fake images into two separate lists, real_files and fake_files. Then, I applied the train_test_split function to each of these lists individually to create separate training and testing sets for real and fake images.

Above, I have used a test set size of 0.2, meaning that 20% of the total data is reserved for testing, while the remaining 80% is used for training. I also set the random_state parameter to 42 (the true meaning of life haha), which ensures that the data is split consistently every time the code is run, making it more reproducible.

Finally, I combined the real and fake training files and their corresponding labels into a single list each, creating train_files, test_files, train_labels, and test_labels.

There were the following split images: 
        Number of training images:  120
        Number of testing images:  30

**Question 3b**. 

Data augmentation is a way to prevent overfitting and increase the generalization capabilities of your model. We use it so that we can artificially create variations of the data by applying random (but realistic) transformations such as rotation, translation, scaling, flipping, etc. Here are some techniques that we can use to handle out-of-distribution images:

Random Rotation: Randomly rotate some training images by a certain degree.
Random Shifts: Shift the images vertically or horizontally by a certain random amount.
Random Flips: Flip images randomly either horizontally or vertically.
Random Zoom: Randomly zoom inside pictures.
Random Shear: Randomly apply shearing transformations.
Random Brightness, Contrast, Saturation, and Hue adjustment.

In my code, I used libraries like TensorFlow's ImageDataGenerator to perform such transformations. Here is the snippet of code I used: 

datagen = ImageDataGenerator(
    rescale=1. / 255,
    shear_range=0.2,
    zoom_range=0.2,
    horizontal_flip=True)

This performs the following transformations: 
* **Rescaling**: I rescale the pixel values of the image by dividing them by 255 to normalize the pixel values to the range [0, 1], which helps the model converge faster during training
* **Shear Range**: I apply a random shearing transformation to the images. The shear_range parameter controls the angle in radians by which the shearing transformation is applied. I have set it to 0.2 
* **Zoom Range**: I apply a random zoom transformation to the images. The zoom_range parameter specifies the range of zoom factors (ZF) as a float or a tuple of two floats. I have set it to 0.2, which means the ZF will be randomly picked in the range [1 - 0.2, 1 + 0.2]
* **Horizontal Flip**: I have apply a random horizontal flip to the images. This is especially useful when there is no specific orientation for the objects in the images.


**Question 3c**. 

Since I do not have the ground truth labels of the images, I cannot calculate many of the  metrics I normally would, such as accuracy, however, I have saved the predictions and the corresponding image names to a csv file 

