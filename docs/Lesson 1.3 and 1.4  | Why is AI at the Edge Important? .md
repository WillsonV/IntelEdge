## Why is AI at the Edge Important?
- Network impacts
- Latency Considerations
- Security concerns
- Optimizations for local inrefrence.


- Network communication can be expensive (bandwidth, power consumption, etc.) and sometimes impossible (think remote locations or during natural disasters)
- Real-time processing is necessary for applications, like self-driving cars, that can't handle latency in making important decisions
- Edge applications could be using personal data (like health data) that could be sensitive if sent to cloud
- Optimization software, especially made for specific hardware, can help achieve great efficiency with edge AI models


--------------------------------------------------------------------------------------
Lesson 1.4 | Application of Edge AI

There are nearly endless possibilities with the edge.
IoT devices are a big use of the edge.
Not every single app needs it - you can likely wait a second while your voice app goes to ask the server a question, or such as when NASA engineers are processing the latest black hole data.


- The apps which can't handle latency .These apps needs to process  real time data in approx no time.Edge Ai is needed in these type of applications.

-------------------------------------------------------------------------------------
Q) these are reasons for development of the Edge?  
A) Proliferation of devices  
   Need for low-latency compute  
   Need for disconnected devices
   
------------------------------------------------------------------------------------
- lesson 1.5 Applications of Egde AI In various field  
- lesson 1.6 Historical context
-----------------------------------------------------------------------------------
### Lesson 1.6 | Course Structure of Foundation Course 

- First, we’ll start off with pre-trained models available in the OpenVINO™ Open Model Zoo. Even without needing huge amounts of your own data and costly training, you can deploy powerful models already created for many applications.  
- Next, you’ll learn about the Model Optimizer, which can take a model you trained in frameworks such as TensorFlow, PyTorch, Caffe and more, and create an Intermediate Representation (IR) optimized for inference with OpenVINO™ and Intel® hardware.  
- Third, you’ll learn about the Inference Engine, where the actual inference is performed on the IR model.  
- Lastly, we'll hit some more topics on deploying at the edge, including things like handling input streams, processing model outputs, and the lightweight MQTT architecture used to publish data from your edge models to the web.

------------------------------------------------------------------------------------
### Lesson 7 | Big Picture | Why Are the Topics Distinct?

- Pre-trained models can be used to explore your options without the need to train a model. This pre-trained model can then be used with the Inference Engine, as it will already be in IR format. This can be integrated into your app and deployed at the edge.  
- If you created your own model, or are leveraging a model not already in IR format (TensorFlow, PyTorch, Caffe, MXNet, etc), use the Model Optimizer first. This will then feed to the Inference Engine, which can be integrated into your app and deployed at the edge.  
- While you'll be able to perform some amazingly efficient inference after feeding into the Inference Engine, you'll still want to appropriately handle the output for the edge application, and that's what we'll hit in the final lesson.

* see slides from this lesson for better understanding

- use cases of diffrent software used in this course?  
    - Model Optimizer----->  convert model(to IR) for further use with toolkit.  
    - Open Model Zoo------> Obtain a pre tarined model from here.  
    - Inference Engine ------> Performs inference on the IR.
    
    --------------------------------------------------------------------------------
    ### Lesson 1.8 | Prerequisites

- Prerequisites:  
  - Understand some of the basics of computer vision and how AI models are created.  
   - Basic Python or C++ experience. This first course is mainly in Python, although C++ can be used with the Intel® Distribution of     OpenVINO™ Toolkit easily as well (and can be faster in a completed app!).  
   - We will not be training models in this course, as our focus is on optimization & deployment at the edge.  
    Classroom workspaces will be available for exercises, so no set-up required if you plan to use them.  
    - Local Set-up  
    Make sure to make note of the hardware requirements for the Intel® Distribution of OpenVINO™ Toolkit if you want to work locally.
If you do want to do the exercises on your local machine (or perhaps even on a set-up like a Raspberry Pi with an Intel® Neural Compute Stick 2), you can follow the instructions below for your operating system.  
Note: The classroom workspaces in this course use the 2019 R3 version of the toolkit, so there may be some variance in syntax from newer versions.

- Download the Toolkit  
  - Intel® DevCloud - Edge  
  There is also the new Intel® DevCloud platform for testing out edge environments. This allows you to have access to a range of Intel® hardware such as CPUs, GPUs, FPGAs, Neural Compute Stick, and more. Later courses will get more into the hardware side of things, but this another option for working with an edge environment.

