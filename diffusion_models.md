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
### Imagen
https://arxiv.org/pdf/2205.11487.pdf
# VAE models
### Dall-E
https://arxiv.org/pdf/2102.12092.pdf\
### Dall-E 2
https://cdn.openai.com/papers/dall-e-2.pdf
### Dall-E 3
https://cdn.openai.com/papers/dall-e-3.pdf

# Variational Autoencoders
It has an encoder and decoder. The encoder learns the latent representations of the input images and the decoder learns to reconstruct the original images from latents.
