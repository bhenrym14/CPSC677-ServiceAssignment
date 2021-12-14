# Modern Techniques For Long Document Summarization With Transformer Models

Long document summarization has been a challenging task for long transformer models due to the long input context. Attention mechanisms scale quadratically in computational complexity with respect to sequence length. There have been many attempts to simplify the attention mechanism or otherwise alleviate the computation bottleneck while maintaining the representatation capacity/expressiveness of the attention mechanism that makes transformers successful in so many tasks. Here are some modern approaches, by year of publication.


### 2019

#### Transformer XL (2019) https://arxiv.org/pdf/1901.02860.pdf
- Employs a recurrence mechanism by reusing model states in multiple forward passes.

#### Adaptive Attention Span (2019) https://arxiv.org/pdf/1905.07799.pdf
- Enables the attention span of each attention head to differ.
- Reduced attention spans are learned, reducing computational complexity of the attention mechanism

#### Sparse Transformers (2019) https://arxiv.org/pdf/1904.10509.pdf
- Sparsifies the self attention matrix by matrix factorization. Produces dense local attention while remaining sparse at a distance, reducing computation complexity/memory footprint.

#### BP-Transformer (2019) https://arxiv.org/pdf/1911.04070.pdf
- Uses binary partitioning to derive a fine-to-course attention mechanism.
- Local scales use finer density, while longer scales are more sparse.
- O(d L log(L/d))

#### Dynamic Convolution (2019) https://arxiv.org/pdf/1901.10430.pdf
- Predicts convolution kernels based on current time step to infer context element salience.
- Scales linearly with input length.

### 2020

#### Reformer (2020) https://arxiv.org/pdf/2001.04451.pdf
- Eschews scaled dot-product attention to a locality-sensitive hashing approach.
- Uses a reversible residual approach that reduces activation storage requirements.
- O(L log L)

#### Compressive Transformers (2020) https://arxiv.org/pdf/1911.05507.pdf
- Compresses distant information/memory; enables model to attend to a lower dimensional representation of the context.

#### Routing Transformers (2020) https://arxiv.org/pdf/2003.05997.pdf
- Learns optimal sparse attention patterns via an online k-means algorithm rather than predefining them.
- O(L^1.5 d)

#### Longformer (2020) https://arxiv.org/pdf/2004.05150.pdf
- Develops a sparse attention mechanism by composing a dense local attention, a dilated attention, and a global attention mechanism. The global attention mechanism enables certain important tokens to have global attention when appropriate.

### 2021

#### BigBird (2021) https://arxiv.org/pdf/2007.14062.pdf
- Develops a sparse attention mechanism that achieves linear complexity with respect to sequence length.
- Rigorously demonstrate Turing completeness of their attention mechanism, adding that permitting global attention (dense) for select tokens is highly beneficial.
