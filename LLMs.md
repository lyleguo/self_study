# Models

### LLaMA
https://arxiv.org/pdf/2302.13971.pdf \
Key takeaways
- Train on larger corpus
- Normalize the input of each layer
- SwiGLU activation
  - $SwiGLU(x) = x * sigmoid(beta * x) + (1 - sigmoid(beta * x)) * (Wx + b)$
- Rotary embeddings
### LLaMA-2
https://arxiv.org/pdf/2307.09288.pdf \
Compare with LLaMA,
- It is trained on more data
- It applied reinforcement learning with human feedback (RLHF)
### Vicuna
https://lmsys.org/blog/2023-03-30-vicuna/ \
It finetunes LLaMA on conversation data from ShareGPT.com
### LLaVA
https://arxiv.org/pdf/2304.08485.pdf \
- Use GPT/ChatGPT to convert captions into instruction-following format
- First train model for image captioning to help it align the features
- Fine-tune the model for question answering
