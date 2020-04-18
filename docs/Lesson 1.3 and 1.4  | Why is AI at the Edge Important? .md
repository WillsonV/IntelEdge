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
### Lesson 1.7 | Course Structure of Foundation Course 

- First, we’ll start off with pre-trained models available in the OpenVINO™ Open Model Zoo. Even without needing huge amounts of your own data and costly training, you can deploy powerful models already created for many applications.  
- Next, you’ll learn about the Model Optimizer, which can take a model you trained in frameworks such as TensorFlow, PyTorch, Caffe and more, and create an Intermediate Representation (IR) optimized for inference with OpenVINO™ and Intel® hardware.  
- Third, you’ll learn about the Inference Engine, where the actual inference is performed on the IR model.  
- Lastly, we'll hit some more topics on deploying at the edge, including things like handling input streams, processing model outputs, and the lightweight MQTT architecture used to publish data from your edge models to the web.
