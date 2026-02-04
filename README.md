# Rectified-Flow-MNIST
Let's implement rectified flow on MNIST in a very simple way using PyTorch and a lightweight UNet-style backbone.
To make the code easy to read and understand, this project leaves out more complex parts often used in larger models (like self-attention layers or very deep UNet structures) and focuses only on the essentials.  
  
  
To be honest, the loss appears as follows:  
```text  
epoch:  10 | loss: 0.06156  
epoch:  20 | loss: 0.05869  
...  
epoch:  60 | loss: 0.05594 
epoch:  70 | loss: 0.05547
```
but I'm not sure what the standard is.  

