#### L4.2

1. The Inference Engine runs the actual inference on a model.
2. It only works with the Intermediate Representations that come from the Model Optimizer, or the Intel® Pre-Trained Models in OpenVINO™ that are already in IR format.
[alt Image ]

##### Model Optimizer vs Inference Engine
Where the Model Optimizer made some improvements to size and complexity of the models to improve memory and computation times, the Inference Engine provides hardware-based optimizations to get even further improvements from a model.
This really empowers your application to run at the edge and use up as little of device resources as possible.

##### Inference Engine integration into your edge application
The Inference Engine has a straightforward API to allow easy integration into your edge application. The Inference Engine itself is actually built in C++ (at least for the CPU version), leading to overall faster operations, 
However, it is very common to utilize the built-in Python wrapper to interact with it in Python code
