# Fundamentals
## Forward Process
Given an image $x_0$, we define the forward process by adding noise to it step by step. At each step, we have\
$$q(x_t|x_{t-1})=N(x_t;\mu_t=\sqrt{1-\beta_t}x_{t-1},\Sigma_t=\beta_tI)$$
Accumulatively, at the end step T\
$$q(x_{1:T}|x_0)=\prod_{t=1}^Tq(x_t|x_{t-1})$$
Define $\alpha_t=1-\beta_t$ and $\hat{\alpha_t}= \prod_{s=0}^T \alpha_t$, using a reparameterization trick, we have\
$$x_t=\sqrt{\hat{\alpha_t}}x_0+\sqrt{1-\hat{\alpha_t}}\epsilon_0$$
Note that it uses the fact that the sum of two Gaussians remains Gaussian and its mean/variance is the sum of the two means/variances.

# Important Diffusion Models
### Stable Diffusion
https://arxiv.org/abs/2112.10752 \
The main contribution is that, instead of directly applying models to the whole image, they apply their model to latents. The key methods include
- Train an encoder-decoder model to learn the latents
- Time-conditional U-Net
- Augment U-Net backbones with cross-attention mechanism
### Stable Diffusion 2
Compared with previous ones, it
- Changes the text encoder
- Allow negative prompts
### Stable Diffusion XL
compare with previous ones, it
- Uses two text encoders
- Enlarges the U-Net
- Uses a base model for generation and a refiner model for improvement
### GLIDE
https://arxiv.org/pdf/2112.10741.pdf\
Apply guided diffusion model to text-guided image synthesis. Compare CLIP guidance and classifier-free guidance and found that the latter yields better results.
### IMAGEN
https://arxiv.org/pdf/2205.11487.pdf\
The key takeaways are
- It uses frozen LLM as text encoder (T5-XXL)
- Dynamic Thresholding
  - Static Thresholding (clip x to $\[-1,1\]$) combined with large guidance weights prevents generating blank images.
  - For Dynamic Thresholding, at each timestep, setup a percentile of pixel value $s$ and use $s$ to normalize x to $\[-1,1\]$ 
- Efficient U-Net
  - Use more residue blocks at low resolution
### 
RE-IMAGEN: RETRIEVAL-AUGMENTED TEXT-TO-IMAGE GENERATOR
https://openreview.net/pdf?id=XSEBx0iSjFQ\
It is a retrival-augmented diffusion model. For each target word in the prompt, it searches for related images in the database. In detail, it construct a <image,text> database for all target words. The model searches for top-k related pairs as additional inputs. The searching is done by computing the similarity between the input prompt and text in pairs. The pairs are encoded using the same encoder in the diffusion U-Net.
### Composable Diffusion
https://arxiv.org/pdf/2206.01714.pdf\
It explains that diffusion models can be viewed as energy-based models (EBM). Hence, methods to compose EBMs can be applied to diffusion models. In this paper, they combine multiple latents which represent different concepts by adding them up, like the energies. The resulting image shows the mixed effect of the combined concepts. These encoded features are combined with the latent features using cross-attention modules. It designs a schedule of using text prompt and neighbors.
### GLIGEN
https://arxiv.org/pdf/2301.07093.pdf \
It primarily studies text-to-image generation conditioned on bounding boxes. It also allows other conditions together with bounding boxes, such as reference images and texts.
### Reduce, Reuse, Recycle
https://arxiv.org/pdf/2302.11552.pdf \
It points out a problem of composable diffusion and shows that the latents cannot be simply added together. It will lead to inferior results. Instead, they propose a Markov Chain Monte Carlo (MCMC) approach to get the combined latents. Specifically, within each denosing step, there is an $N$-round MCMC process.

# VAE models
### Dall-E
https://arxiv.org/pdf/2102.12092.pdf\
Two stage training process
1. Train a VAE (image only)
2. Concatenate text tokens with image features and train a transformer to model the joint distribution (Fix the VAE)
### Dall-E 2
https://cdn.openai.com/papers/dall-e-2.pdf \
Key takeaways
- Consists of two models: a prior model that generates CLIP image embeddings given a text caption; a decoder that generates image given CLIP image embeddings
- For the decoder, the CLIP embeddings are added to time embedding. The CLIP embeddings are also projected and concatenated with the text encoder outputs
- For the prior model, it compares autoregressive model and diffusion model
### Dall-E 3
https://cdn.openai.com/papers/dall-e-3.pdf \
Rewrite the prompts into detailed ones.

# Variational Autoencoders
It has an encoder and decoder. The encoder learns the latent representations of the input images and the decoder learns to reconstruct the original images from latents.
