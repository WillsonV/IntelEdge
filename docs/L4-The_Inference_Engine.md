#### L4.2

>From Quiz question </br>
Q) Inference Engine?  </br>  
A) It provides a library of computer vision functions and performs the inference on a model.


1. The Inference Engine runs the actual inference on a model.
2. It only works with the Intermediate Representations that come from the Model Optimizer, or the Intel® Pre-Trained Models in OpenVINO™ that are already in IR format.
[alt Image ]

##### Model Optimizer vs Inference Engine
Where the Model Optimizer made some improvements to size and complexity of the models to improve memory and computation times, the Inference Engine provides hardware-based optimizations to get even further improvements from a model.
This really empowers your application to run at the edge and use up as little of device resources as possible.

##### Inference Engine integration into your edge application
The Inference Engine has a straightforward API to allow easy integration into your edge application. The Inference Engine itself is actually built in C++ (at least for the CPU version), leading to overall faster operations, 
However, it is very common to utilize the built-in Python wrapper to interact with it in Python code


---------------------------------------------------------------------------------------------------------------------------------
## L4.3 supported devices for the Inference Engine
 Supported devices for the Inference Engineare a variety of such devices: CPUs, including integrated graphics processors, GPUs, FPGAs, and VPUs.
 
 - FPGAs  
 FPGAs, or Field Programmable Gate Arrays, are able to be further configured by a customer after manufacturing. Hence the “field programmable” part of the name.
 
 
 - VPUs  
 VPUs, or Vision Processing Units, are going to be like the Intel® Neural Compute Stick. They are small, but powerful devices that can be plugged into other hardware, for the specific purpose of accelerating computer vision tasks
 
 
 - Differences Among Hardware  
 Mostly, how the Inference Engine operates on one device will be the same as other supported devices; however, you may remember me mentioning a CPU extension in the last lesson. That’s one difference, that a CPU extension can be added to support additional layers when the Inference Engine is used on a CPU.

There are also some differences among supported layers by device, which is linked to at the bottom of this page. Another important one to note is regarding when you use an Intel® Neural Compute Stick (NCS). An easy, fairly low-cost method of testing out an edge app locally, outside of your own computer is to use the NCS2 with a Raspberry Pi. The Model Optimizer is not supported directly with this combination, so you may need to create an Intermediate Representation on another system first, although there are some instructions for one way to do so on-device. The Inference Engine itself is still supported with this combination.

-----------------------------------------------------------------------------------------------------------------------------------

##### L4.4 Using the Inference Engine with an IR

To load an IR into the Inference Engine, you’ll mostly work with two classes in the openvino.inference_engine library (if using Python):

- **IECore**, which is the Python wrapper to work with the Inference Engine.
- **IENetwork**, which is what will initially hold the network and get loaded into IECore.

The next step after importing is to set a couple variables to actually use the IECore and IENetwork.
 - In the IECore documentation, no arguments are needed to initialize. [IECore()]
 - To use IENetwork, you need to load arguments named model and weights to initialize - the XML and Binary files that make up the model’s Intermediate Representation.[ IENetwork (model,weights)]
 
 
 ###### Check Supported Layers
 
 In the IECore documentation, there was another function called ```query_network``` , which takes in arguments </br>   
 - IENetwork  
 - a device name  
 - returns a list of layers the Inference Engine supports.
 
 The device_name argument is just a string for which device is being used - ”CPU”, ”GPU”, ”FPGA”, or ”MYRIAD” (which applies for the  Neural Compute Stick).
 
  > You can then iterate through the layers in the IENetwork you created, and check whether they are in the supported layers list. If a layer was not supported, a ```CPU extension``` may be able to help
  
 ##### CPU extension
 
 
  
  
  
    
    
    
    
 



