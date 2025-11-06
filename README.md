# Principal Component Analysis

![San Agustín en oración by Jusepe de Ribera, 1636](cover.jpg)

In progress

The goal of principal component analysis is to take some model and delete the least important features. It transforms a dataset with potentially correlated features into a new set of uncorrelated variables called principal components. After performing this operation, we are left with a simpler model that is easier to interpret, more robust, less overfitted, faster to train, *and* easier to intuit. Basically, the point of this analysis is to reduce the dimensionality of the data and leave us with only the principal components.

## Math

- Center the data (subtract the mean of each feature).
- Compute the covariance matrix of the data.
- Perform eigen-decomposition of the covariance matrix to get eigenvectors (directions) and eigenvalues (variance along each direction).
- Sort eigenvectors by descending eigenvalue magnitude; these become the principal components.
- Project the original data onto the top
- components to reduce dimensionality while retaining maximal variance.

Result: after diagonalizing the covariance matrix, we have some eigenvectors. The ones with the lowest corresponding eigenvalues are the least important. Using only the top k eigenvectors, we can project our data into a lower-dimensional space. We get rid of collinearity since they fall within the subspace spanned by the orthogonal eigenvectors.
