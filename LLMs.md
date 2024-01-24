# Models
## LLMs
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
## Parameter Efficient Fine Tuning (PEFT)
### LORA
It makes a hypothesis that the updated weight matrix is the original matrxi added by a low-rank matrix. The low-rank matrix is decomposed as the product of two smaller matrices $A$ and $B$. During training, we fix the original weights and only train $A$ and $B$.
### PrefixTuning	
Append learnable prefix vectors
### PrefixTuningv2	
Apply continuous prompts for evrey layer instead of only input
### PromptTuning	
Use a fixed prompt of special tokens and only update the embeddings of these tokens
### AdaLORA	
- Use SVD
- Compute the importance score for each vector. Mask out the less important ones.
- An auxilary loss to enforce P,Q to be orthonormal
- The importance score is the momentum of gradient-weight product
- b value in top_b first increases then decreases
### P-Tuning	
Concatenate discrete prompt embeddings and continuous prompt embeddings
### LOFTQ	
- Define Q matri as the quantized weight
- Apply SVD to (W-Q)
- Update low-rank mat A,B"
### OFT	
- Fine-tuned weights are R*W where R is orthogonal matrix
- Train to minimize hyperspherical energy
- R as diagonal blocks"
### IA3	
- Introduce new learned vectors to attention
- element-wise multiplication of model's activation against a learned vector"
### KronA	
- Use Kronecker product to replace low rank product
- Kronecker product decomposition keeps the rank. And one can avoid computing W
- Add a relu and use residue structure for FFN "
