**Question 1a**. Considerations that went into deciding what data to collect????

When building a dataset for detecting deepfake face images, it's important to consider several key factors to ensure that the resulting machine learning models are robust, reliable, and ethical. Here are the key considerations:

1. **Diversity**
A diverse dataset is crucial for training a model that can generalize well across a wide range of inputs. The dataset should include images that vary in:

* Age: Include faces of individuals from different age groups.
* Gender: Ensure a balanced representation of different genders.
* Skin Color: Incorporate a wide spectrum of skin tones.
* Race / Ethnicity: incorporating a wide distribution of ethnicities. 
* Facial Expressions: Include varying facial expressions to ensure the model can handle different expressions.
* Lighting Conditions: Include images taken under different lighting conditions to ensure the model is robust to changes in lighting.

**NOTE**: The debate on skin color vs race / ethnicity is on-going and should be selected based on experimental needs. Several papers have shown that using skin color as a proxy to racial or ethnicity grouping. However, while skin color can be easily computed without subjective annotations, it has many limitations such as, illumination and lighting conditions, within-group variations of skin color are massive, race is multidimensional while skin color is uni-dimensional 

2. **Bias**
Bias in the dataset can lead to biased outcomes from the model. Biased datasets have been a prominent issue in machine learning and can result in unfair or discriminatory practices. It's important to actively identify and mitigate biases during dataset creation. This can be done by:

* Ensuring a balanced representation of different groups (as mentioned in the diversity section).
* Evaluating and addressing potential sources of bias during data collection.

3. **Quality**
The quality of the images in the dataset plays a major role in the performance of the model. Images should be:

* Clear: The facial features should be clearly visible.
* Well-lit: Good lighting is important for discerning facial features.
* High Resolution: Low-resolution images may lack the detail necessary for accurate deepfake detection.

4. **Variety in Deepfake Sources**
Deepfake technologies vary greatly in quality and method. Therefore, to train a model that can detect a wide range of deepfakes, it's important to include fake images from a variety of sources. This helps ensure the model isn't overfitting to a specific type or quality of deepfake.

5. **Ethics and Privacy**
Ethical considerations should be at the forefront when creating the dataset. We must:

* Ensure the images are publicly available.
* Respect privacy regulations and not use images without proper consent.
* Respect copyrights and not use images without proper authorization.
* By taking these factors into consideration, we can build a robust and ethical dataset for deepfake detection.


--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


**Question 1b**. How you went about collecting the data????

1. I searched across various platforms like GitHub, Kaggle, and research publications for relevant datasets. This included looking for datasets that specifically contained real and fake face images, as well as datasets that provided a diverse set of facial images in terms of demographics, expressions, and quality. The following datasets are just a sample of what was looked at for this project:

* https://openaccess.thecvf.com/content/WACV2021/papers/Karkkainen_FairFace_Face_Attribute_Dataset_for_Balanced_Race_Gender_and_Age_WACV_2021_paper.pdf
* https://github.com/deepfakeinthewild/deepfake-in-the-wild
* https://github.com/SkyThonk/real-and-fake-face-detection 
* https://github.com/microsoft/FaceSynthetics (this is for synthetic faces which isn't relevant in this scenario)
* https://www.kaggle.com/datasets/ciplab/real-and-fake-face-detection?resource=download

**Others were looked at but not used**

2. If this were in a professional environment there should be extensive testing of the datasets on their biases and distribution of **important metrics** (pre-determined by researchers) to make sure the dataset is wholistic

3. The dataset used contains **expert-generated high-quality** photoshopped face images. The images are composite of different faces, separated by eyes, nose, mouth, or whole face.


--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**Question 1c**. What other labels would you consider? Explain a simple method to sample a uniform dataset given the labels???

**LABELS** 
* **Demographics**: Age, gender, ethnicity, etc. These could be useful for ensuring the model works well across diverse populations and doesn't learn biased representations.

* **Facial Expressions**: Happy, sad, angry, surprised, etc. These could be useful for emotion detection tasks.

* **Facial Landmarks**: Locations of eyes, nose, mouth, etc. These could be useful for tasks that involve understanding facial structure, such as facial recognition or facial feature editing.

* **Lighting Conditions**: Bright, dim, harsh shadows, etc. These could be useful for ensuring the model works under different lighting conditions.

* **Image Quality**: High resolution, low resolution, blurry, etc. These could be useful for ensuring the model works with different quality images.

* **Pose**: Frontal, profile, tilted, etc. These could be useful for ensuring the model works with faces in different orientations.


* 
**METHOD**: for sampling a uniform dataset in the i.i.d sense given the labels

* Identify the smallest class size: Count the number of samples in each label category and find the smallest class size. Let's call this number n.

* Sample n instances from each label category: Randomly select n instances from each label category to create a balanced dataset. This ensures that each label category is represented equally and the dataset is uniform.

* Combine the sampled instances from each label category: Merge the sampled instances from each label category to form the final uniform dataset.

**By following this method, you can create a dataset where each label category is represented equally, promoting a balanced and unbiased training process.**

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**Question 1d**. What API used to store and organize meta information about the dataset????

API used: I used Kaggle API for obtaining the dataset

Datastructures used: pandas dataframe, numpy arrays and tensors were used for the store the data


