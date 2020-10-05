#### Take care of missing data

- One way of taking care of missing values is to remove data
  - Removing upto 1% of data will not affect training
- Second way is to fill data based on available data
  - Use sklearn imputer for SimpleImputer or IterativeImputer
  - Using this we can fill values by setting strategy as mean, most_frequent, constant
  - IterativeImputer is more sophesticated as it creates a function of all columns to find a value.

[see more here](https://scikit-learn.org/stable/modules/impute.html)

#### Remove duplicate data

- Duplicate data introduces a bias, which leads to bad models.

#### Sampling and balancing data

- Sometimes dataset could be too large, hence it is better to take a smaller sample of the dataset and use a more expensive machine learning algorithm.
- It is important to balance out the number of entries for categorical data, otherwise this would introduce a bias.

#### Encoding categorical data

- Use encoders to convert categorical / string data to numerical value
- [Label Encoder](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.LabelEncoder.html)
  - Gives each category/class a number (might not be good for come situations)
- [One hot encoder](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.OneHotEncoder.html)
  - Creates a separate column for each category (increases training time)
- Additional resources
  - [kaggle-examples](https://www.kaggle.com/discdiver/category-encoders-examples)
  - [kaggle-benchmark](https://www.kaggle.com/subinium/11-categorical-encoders-and-benchmark)

#### Feature scaling

- Model performs better when numerical data are within a certain range
- Better if all features have values in similar range as to not introduce any bias.

- Normalization

  - Scale each value to a certain range (e.g. range 0-1)
  - [mix max scalar](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.MinMaxScaler.html)

- Standardization
  - Scales each value by subtracting with mean and dividing by standard deviation
  - [standard scalar](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.StandardScaler.html)
- [Resources](https://machinelearningmastery.com/standardscaler-and-minmaxscaler-transforms-in-python/)

#### Dimensionality reduction

- Real world scenarios provide large number of features.
- This step helps in reducing the number of features to be taken for model learning.

#### Split the data

- Dataset has to be split into
  - training (model learns from this data)
  - validation (used to improve hyperpaters. the model does not learn from this data)
  - testing (untouched until hyperparameters are tuned. this is the final check to see how the model would perform in real world)
