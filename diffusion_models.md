# Important Diffusion Models
## Text-to-Image Generation
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
### Dall-E
https://arxiv.org/pdf/2102.12092.pdf\
