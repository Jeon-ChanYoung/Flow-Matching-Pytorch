# Flow-Matching-Pytorch
Let's build an lightweight generative model using the “Flow Matching” algorithm. Our goal is perfect reconstruction, and we'll see how well it restores fine details through the denoising process. We use a pixel art dataset (shape: 3x16x16).  
  
There are currently four versions available. You can view them as ipynb files, and pre-trained pth files can be downloaded from the Releases.  

- Flow Matching Basic
- Flow Matching Enhanced
- Latent Flow Matching
- Latent Flow Matching + VQ-VAE

<br> 

## Flow Matching Basic 
### Result
<img src="assets/real_vs_generated.png" alt="Real vs Generated" />

### Denoising
<img src="assets/denoising.gif" alt="Denoising Process" />

Good, but the slight pixel differences and rendering are disappointing. 
  
<br>

## Flow Matching Enhanced
The Enhanced version incorporates the following improvements over the previous version:  
- Exponential Moving Average (EMA)  
- Classifier Free Guidance (CFG)  
- Logit Normal Sampling (Sigmoid)  
- Max Pooling -> Strided Convolutions
  
### Result
<img src="assets/real_vs_generated1.png" alt="Real vs Generated" />

### Denoising
<img src="assets/denoising1.gif" alt="Denoising Process" />

<br>

## Latent Flow Matching  
Rather than working in pixel space, we pre-train a VAE and apply Flow Matching in the latent space (shape: (3, 16, 16) -> (8, 4, 4)). The UNet predicts velocity fields over compact latent vectors instead of raw pixels, making training more efficient while capturing higher-level structure.  
  
<br>  

### Result  
<img src="assets/real_vs_generated2.png" alt="Real vs Generated" />  

### Denoising
<img src="assets/denoising2.gif" alt="Denoising Process" />
  
<br>  

## Latent Flow Matching + VQ-VAE  
What if we replace the continuous VAE with a discrete VQ-VAE. The codebook indices are discrete, but the codebook vectors themselves live in continuous R^D space so Flow Matching still works. We train on pre-quantization outputs (z_e) for smooth optimization, then re-quantize before decoding.  

<br>
  
### Result
<img src="assets/real_vs_generated3.png" alt="Real vs Generated" />

### Denoising
<img src="assets/denoising3.gif" alt="Denoising Process" />
