# Flow-Matching-Pytorch
Let's build an lightweight generative model using the “Flow Matching” algorithm. Our goal is perfect reconstruction, and we'll see how well it restores fine details through the denoising process. We use a pixel art dataset (shape: 3x16x16).  

<br> 

## Flow Matching Basic 
### Result
<img src="assets/real_vs_generated.png" alt="Real vs Generated" />

### Denoising
<img src="assets/denoising.gif" alt="Denoising Process" />

Good, but the slight pixel differences and rendering are disappointing. The Enhanced version incorporates the following improvements over the previous version:  
- Exponential Moving Average (EMA)  
- Classifier Free Guidance (CFG)  
- Logit Normal Sampling (Sigmoid)  
- Max Pooling → Strided Convolutions
  
<br>

## Flow Matching Enhanced
### Result
<img src="assets/real_vs_generated1.png" alt="Real vs Generated" />

### Denoising
<img src="assets/denoising1.gif" alt="Denoising Process" />

<br>

## Latent Flow Matching  
Pre-train the VAE and apply Flow Matching in the latent space (shape: (3, 16, 16) -> (4, 8, 8)).  
<br>  

### Result  
<img src="assets/real_vs_generated2.png" alt="Real vs Generated" />  

### Denoising
<img src="assets/denoising2.gif" alt="Denoising Process" />
