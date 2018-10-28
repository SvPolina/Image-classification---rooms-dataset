Image-classification - Rooms-dataset

Data set: 
https://dataturks.com/projects/sheerun/rooms
The Rooms Dataset has around ~10 k images belonging to 6 classes with each image has an annotation associated with it.
This makes it roughly ~1700 images per class-  sufficient amount of the data required to train a Convolution Neural Net 
classifier. 
The downloaded json file contained among the info for each enry the URL to a given image and it's label. As a first step we've created a
folder with these images. 

Learning process:
Though the sufficient amount of data, as a first step we've decided to use the concept of Transfer Learning. We've used a pre
pretrained model (ResNet-18) as our classifier.The justification is as follows: The lower layers of the conv net are activated with 
the primitive features (texture,color etc.) which makes them sharable with other applications. So all layers except of the last fully 
connected were frozen while for the last layer we've specified the number of learned classses as 6.
This resulted in accuracy achieved on the test set containing 3309 images of:74% (2 training epochs)
As a next step we've decided to train the model from a scratch, we've used the not pretrained ResNet18 (keeping it's structure with the 
change of  num. classes at the last Linear layer) the learning process is detailed in the notebook. 
at this experiment we've received an accuracy of :49% (2 training epochs) which is definitely better than a random guess but of course 
is not sufficient.



