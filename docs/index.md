
layout: page
title: "Willson Intel"
permalink: /IntelEdge/

<a href="https://willsonv.github.io/IntelEdge/L4  The Inference Engine.md">L4  The Inference Engine</a>
[l4](L4  The Inference Engine.md)

L2.9
#Optimizations on the Pre-Trained Models

#Precisions:
Precisions are related to floating point values - less precision means less memory used by the model, and less compute resources.
However, there are some trade-offs with accuracy when using lower precision.

#fusion:
fusion, where multiple layers can be fused into a single operation.
These are achieved through the Model Optimizer in OpenVINO™, although the Pre-Trained Models have already been run through that process
L2.10 
choosing right model

L2.11

The pre-processing needed for a network will vary, but usually this is something you can check out in any related documentation,
including in the OpenVINO™ Toolkit documentation. 
It can even matter what library you use to load an image or frame - OpenCV, which we’ll use to read and handle images in this course, reads them in the BGR format, which may not match the RGB images some networks may have used to train with.

Outside of channel order, you also need to consider image size, and the order of the image data, such as whether the color channels come first or last in the dimensions. Certain models may require a certain normalization of the images for input, such as pixel values between 0 and 1, although some networks also do this as their first layer.

In OpenCV, you can use cv2.imread to read in images in BGR format, and cv2.resize to resize them. The images will be similar to a numpy array, so you can also use array functions like .transpose and .reshape on them as well, which are useful for switching the array dimension order.

#L2.12 | Pre Processing inputs 

#L2.13  | solution to L2.12

Using the documentation pages for each model, I ended up noticing they needed essentially the same preprocessing, 
outside of the height and width of the input to the network. 
The images coming from cv2.imread were already going to be BGR, and all the models wanted BGR inputs, 
so I didn't need to do anything there. However, each image was coming in as height x width x channels,
and each of these networks wanted channels first, along with an extra dimension at the start for batch size.

So, for each network, the preprocessing needed to 
1) re-size the image, 
2) move the channels from last to first,and 
3) add an extra dimension of 1 to the start.
Here is the function I created for this, which I could call for each separate network.




def preprocessing(input_image, height, width):
    '''
    Given an input image, height and width:
    - Resize to height and width
    - Transpose the final "channel" dimension to be first
    - Reshape the image to add a "batch" of 1 at the start 
    '''
    image = cv2.resize(input_image, (width, height))
    image = image.transpose((2,0,1))
    image = image.reshape(1, 3, height, width)

    return image
 
    Then, for each model, I can just call this function with the height and width from the documentation:
Human Pose

preprocessed_image = preprocessing(preprocessed_image, 256, 456)

Text Detection

preprocessed_image = preprocessing(preprocessed_image, 768, 1280)

Car Meta

preprocessed_image = preprocessing(preprocessed_image, 72, 72)


<a href="https://willsonv.github.io/IntelEdge/L4.md">Page 2</a>

[asx](L4.md)
