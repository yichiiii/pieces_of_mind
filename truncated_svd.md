### Truncated SVD

In SVD, we know that we can decompose an arbitrary $m*n$ matrix $A$ into the product

$$A = U \Sigma V^T$$

where $U, V$ are $m*m$, $n*n$ orthogonal matrix, respectively. The diagonal components of $\Sigma$ is the singular value of matrix $A$.

Suppose the row of $A$ represents the different objects we want to study (different words, different species of animals, etc.), and the column of $A$ represents the different attributes of the object. More often than not $n$ is a huge number, and we do not want to study all the $n$ attributes in question. We want to come up with a method to suppress $n$ to a small number, like 2. We will denote this number as $k$.

What shall we do? We can extract the largest $k$ singular values, discard the rest, and construct a new singular value matrix $\Sigma_k$, which is $k*k$. Thus, we have

$$A \approx A_k = U_k \Sigma_k V^T_k$$

with $U_k$ being $m*k$ and $V^T$ being $k*n$.

$A_k$ approximates $A$ well, but it is still $m*n$.

Consider $U_k \Sigma_k$, which is a matrix of $m*k$. This can be a good approximation to our system.

Why? Remember when we do the SVD, the columns of $U$ is a set of eigenvectors, whose eigenvalues are the square of the singular values, which are the characteristics of our system. By discarding the less significant singular values, alongside their eigenvectors, we are suppressing the less significant components of our system, only keeping the most important ones.

In conclusion, $U_k \Sigma_k$ is a good compression of our original matrix $A$.