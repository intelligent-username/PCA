# Principal Component Analysis

`*In progress`

![Roman Capriccio The Pantheon and Other Monuments by Giovanni, 1739](cover.jpg)

The goal of principal component analysis is to take some predictive model simplify it by deleting the least important features. We analyze the current features and see which ones have the least variance, and then construct new principal components that capture the maximal variance. It transforms a dataset with potentially correlated features into a new set of uncorrelated variables called principal components. After performing this operation, we are left with a simpler model that is easier to interpret, more robust, less overfitted, faster to train, *and* easier to intuit. Basically, the point of this analysis is to reduce the dimensionality of the data and leave us with only the principal components.

## Math

- Center the data (subtract the mean of each feature).
- Compute the covariance matrix of the data.
- Perform eigen-decomposition of the covariance matrix to get eigenvectors (directions) and eigenvalues (variance along each direction).
- Sort eigenvectors by descending eigenvalue magnitude; these become the principal components.
- Project the original data onto the top components to reduce dimensionality while retaining maximal variance.
- Ensure the vectors are normalized and orthogonal.

Result: after diagonalizing the covariance matrix, we have some eigenvectors. The ones with the lowest corresponding eigenvalues are the least important. Using only the top k eigenvectors, we can project our data into a lower-dimensional space. We get rid of collinearity since they fall within the subspace spanned by the orthogonal eigenvectors.

## Geometric Intuition

## Single Value Decomposition

A strong alternative to eigen-decomposition is singular value decomposition (**SVD**). **SVD** decomposes the data matrix X directly into three matrices: $U$, $S$, and $V^T$, where $U$ contains the left singular vectors, $S$ is a diagonal matrix of singular values, and $V^T$ contains the right singular vectors. The columns of $V$ correspond to the principal components, and the singular values in $S$ indicate the amount of variance captured by each component. By selecting the top $k$ singular values and their corresponding vectors in $V$, we can project the data into a lower-dimensional space while retaining most of the variance.

## Implementation

## Installation

## License

MIT
