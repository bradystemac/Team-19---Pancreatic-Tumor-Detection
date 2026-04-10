# Team-19---Pancreatic-Tumor-Detection
This is the required github repository for BME3053C final project

Motivation:

Pancreatic cancer is a very deadly disease that can go undetected for a significant amount of time before symptoms begin to affect the patient. Due to the position of the pancreas in the upper abdomen, it is difficult and often requires intrusive methods to receive a diagnosis from a medical professional. The use of an AI or computer vision model would be very impactful in the field of radiology due to the increased safety and rates of prevention that could save thousands of lives annually.

Methodology:

We chose to use a subsection of the PanTS dataset in the scope of our project. This dataset is well known in the medical imaging community due to its large scale (36,290 CT scans) and ground truth labels. The first step of our process is to create an equal subsection of tumor and non-tumor images that would eliminate bias due to class size. Then we sliced the middle scan of the 40-scan images to collect singular images that would contain the tumor within the image. A list of ground truth labels (1=tumor/0=no tumor) was created in tandem with the middle scan list to have a label source for the supervised model. Each image was resized to 128x128 pixels as required by machine learning models. These 128x128 images were converted into a 1D array of 16,384-pixel values that we scaled to eliminate bias due to pixel brightness. Our team then trained and tested a SVM model that receives 75% accuracy. 

Downloaded the first 1,000 scans from the original dataset
 Found the number of scans in the first 1,000 that had a tumor present (97 scans)
 Randomly picked a matching number of scans that did not have a tumor present to avoid size bias when training the model
Created tumor case and no tumor case lists that contained the subject id
 Sliced the middle scan from all of the tumor and no tumor cases (most likely to contain the tumor than any other scan in the 3d files)
Created a full list of all of the middle scans and an associated label list that contained the ground truth labels (1=tumor/0=no tumor)
 Compared the volumes of the middle scans
Resized every image to 128x128 pixels
Flattened each image into a 1d array of 16,384 individual values
 Scaled every pixel in every scan to eliminate potential pixel-wise bias due to brightness
 Trained and tested an SVM model (‘C’ = 10, ‘Kernel’, ‘rbf’)

 Results:
 
Our trained SVM model reached 75% accuracy consistently across numerous trials
We trained and tested other models for comparison such as Decision Tree, Logistic Regression, KNN, and Naive Bayes

Decision Tree Test Accuracy (‘max depth’ = 5, ‘min samples split’ = 5): 75%
Logistic Regression Test Accuracy (‘C’ = 1, ‘penalty’ = L2): 70%
KNN Test Accuracy (‘n neighbors’ = 3, ‘weights’ = uniform): 60%
Naive Bayes Test Accuracy: 55%
