Week 2
Word Embeddings

Word embedding vector can replace the sparse one-hot-coded vector input with dense vector, so that it is likely to reduce the dimension (maybe from 10000 to 300)

But the output vector should still be the sparse vector

face encoding: can be applied to any faces, even not seen before
word embedding: a fixed number of vacabulary
But the terminology of encoding and embedding are sometimes used interchangable

The goal of embedding learning is to learn the embedding matrix. The classifier built is not the goal, so even if the classifier accuracy might be low, the embedding matrix learnt might be useful.

Then embedding for a word can be find use matrix mulitipliation (theory), or look up table (in practice). In Keras, one can use the embedding layer to efficiently look up 

The sum for all words in softmax is slow. Hierachical soft max speed up calculations.

In practice will not have a balanced tree. The common words would appear on top, while less popular words deeper in the tree.

Length normalization:
Algorithm may seek for shorter sentences, since adding a word would decrease the probability by multiplying a < 1 number (add a negative number for sum of log). So people usually normalize the score by dividing by $T_y$. In practice, use ${T_y}^{\alpha}$. 

If $\alpha = 0$, there is no normalization

If $\alpha = 1$, full normalization

People usually use value between $0$ and $1$, such as $0.7$

Beam width B, usually have big gain going from 1 -> 3 -> 10. But smaller gain for 100. Very minimial gain for 1000, 3000