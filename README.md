# ML-for-Predicting-Band-Gap
This work was written in Python and was comprised of 5 stages, each in their own Jupyter notebook. The aim was to explore how different regression-based models performed at predicting the band gap of Gallium-containing compounds using differently-processed input datasets. Band gap is an important property for semi-conductor materials which commonly contain Gallium. 

1. Data retrieval from the NOMAD database, data processing and dataset curation
2. Dimensionality Reduction (PCA)
3. Regression Analysis (including Linear, Lasso, Partial Least Squares and Ridge)
4. Epsilon-Support Vector Regression
5. Random Forests

Information on the Ga-containing materials/compounds from the NOMAD database was retrieved, including the chemical compositions, band gap values, band gap types, and the 3-dimenional coordinates of the atoms making up each molecule. The chemical compositions were used to featurise the molecules using the Matminer featurizer package to curate the raw dataset, which captured information on electronic and thermodynamic properties. The raw dataset was then processed in different ways, including being scaled and having repeat structures removed. Dimensionality reduction was performed on the scaled dataset. Different forms of regression were then run on the unscaled, scaled, and reduced datasets, in addition to linear regression being run on the principal components from PCA (i.e., Principal Component Regression, or PCR), to compare how the different forms of regression performed on the differently processed datasets. Support Vector Regression was then performed on the unscaled, scaled and PCA dataset. Random Forests were trained on the same sets of data. GridSearch was used to optimise the hyperparameters for all models. The metrics used for evaluating the models were MSE and 5-fold Cross Validated R^2. 

From the work, we could conclude that Random Forests trained on the full scaled dataset were the most accurate model for predicting the band gap of molecules. Furthermore, Random Forests were able to retain their high prediction score with a lower MSE when being trained on the principal components from PCA, important when considering the computational costs of training. 

Based on this work, further optimisations and alternative approaches can be explored for improving prediction accuracy and generalisability:

- exploring other featurizer packages that embed information on different properties e.g. RDKit, DScribe, MolML
- expand dataset with compounds from other databases e.g. Materials Project
- processing and filter the data to even distribution of data and remove any skews/biases
- using representations to capture global and local structure, such as Coulomb Matrices, which can be used for training simple Deep Learning models (e.g., ANNs)
- using graph representations for training GNNs
