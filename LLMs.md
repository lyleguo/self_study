#Models
###LLaMA
https://arxiv.org/pdf/2302.13971.pdf\
Key takeaways
- Train on larger corpus
- Normalize the input of each layer
- SwiGLU activation
  - $SwiGLU(x) = x * sigmoid(beta * x) + (1 - sigmoid(beta * x)) * (Wx + b)$
- Rotary embeddings
