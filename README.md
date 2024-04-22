# Image_Segmentation_Detecting_Crop_Rows
Detecting Crop Rows
## Dataset Description
Both train and test images are contained in the kaggle competition. Here is an example of input and output image:

Input image:

![image](https://github.com/abhinavztb/Image_Segmentation_Detecting_Crop_Rows/assets/28789570/9f9cb663-3609-4dc7-9172-4de78d367e7c)

Output image:

![image](https://github.com/abhinavztb/Image_Segmentation_Detecting_Crop_Rows/assets/28789570/58be1ae9-279d-43f4-aa6c-98fbe8c18402)


### Your goal is to generate these bounding boxes for segmentation
## Task
The given task is an Image Segmentation problem where we are
detecting crop rows from input images.
## Inputs:
• The input images are provided in Images folder which contain the
.jpeg format of crop field images.
• Train/Test IDs are also provided in a separate CSV file.
• The train labels are .npy files also 320x240 size images with 3
channels but only contain two types of pixel, 0 and 255
The input images and labels are converted and flattened to a 1D array
containing pixel information. Then, the run-length encoding technique is
applied to save space.
## Expected Output:
• Generate labels for the test set in the input images in rle format for
each test id.
The goal of this task is to generate label image features (in RLE format
similar to train_labels.csv) for each ID in the test_features dataset. In
other words, the task is to predict the crop row labels for the test images.
## My Approach
The given problem of detecting crop rows from input images is a
segmentation task, where the goal is to classify each pixel of the image
into one of the two classes - crop row or non-crop row.
To solve this problem, we are using deep convolutional neural network
(CNN) based architectures that are designed for image segmentation
tasks. The following are used:
• Unet model: It is a widely used CNN architecture for image
segmentation tasks. It consists of an encoder and decoder network,
where the encoder network performs down-sampling operations to
capture the high-level features of the input image, and the decoder
network performs up-sampling operations to generate the
segmentation mask. The encoder and decoder networks are
connected through skip connections, which help to preserve the
fine-grained details of the input image during the segmentation
process.
• LinkNet model: It is another CNN architecture designed for image
segmentation tasks. It also consists of an encoder and decoder
network, but it uses a lightweight skip connection block called a
"Link Unit". The Link Unit helps to reduce the computational
complexity of the skip connections while still preserving the fine-
grained details of the input image.
• Segnet model: It is a convolutional neural network that consists of
an encoder and decoder network, similar to the Unet and LinkNet
architectures. However, in Segnet, the decoder network uses
pooling indices from the corresponding encoder network to
perform up-sampling operations. This helps to reduce the number
of parameters and computational complexity of the network.
The approach for solving the given problem using these architectures
would involve the following steps:
1. Pre-processing of the input images - converting them to numpy
arrays, flattening them to 1D arrays, and applying run-length
encoding to save space.
2. Splitting the data into training and testing sets.
3. Training the deep CNN architectures on the training set using the
input images and their corresponding crop row labels.
4. Evaluating the performance of the trained models on the testing set
using the input images and predicting the crop row labels.
5. Converting the predicted crop row labels back to RLE format and
submitting them for evaluation.
