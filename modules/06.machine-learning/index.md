---
Duration: 3 hours
---

# Machine Learning with Spark MLlib

## Spark Ecosystem

![Spark Ecosystem](../02.introduction-and-rdds/image/spark_ecosystem.png)

## Machine Learning With Spark: packages

- spark.mllib:
  - RDD-based (DF functionalities being added)
  - In maintenance since Spark 2.0 (now 3.x)
- spark.ml:
  - Newer
  - DataFrames-based

The term **MLlib** is used for both.

## Machine Learning

Data preparation:
- cleansing
- enrichment
- feature engineering

![Data preparation](./image/data_prep_1.png)

![Data preparation](./image/data_prep.png)

[Resource](https://www.talend.com/resources/what-is-data-preparation/)

Modeling:

![Machine learning tasks](./image/modeling.png)

[Resource](https://noeliagorod.com/2019/05/21/machine-learning-for-everyone-in-simple-words-with-real-world-examples-yes-again/)

## MLlib: Functionalities

ML algorithms include:

- Classification: logistic regression, naive Bayes,...
- Regression: generalized linear regression, survival regression,...
- Decision trees, random forests, and gradient-boosted trees
- Recommendation: alternating least squares (ALS)
- Clustering: K-means, Gaussian mixtures (GMMs)...
- Topic modeling: latent Dirichlet allocation (LDA)
- Frequent itemsets, association rules, and sequential pattern mining

ML workflow utilities include:

- Feature transformations: standardization, normalization, hashing...
- ML Pipeline construction
- Model evaluation and hyper-parameter tuning
- ML persistence: saving and loading models and Pipelines

Other utilities include:

- Distributed linear algebra: SVD, PCA...
- Statistics: summary statistics, hypothesis testing...

[Spark MLlib](https://spark.apache.org/mllib/)
[ML guide](https://spark.apache.org/docs/latest/ml-guide.html)

## When do we choose ML with Spark?

Pros:
- We can process big datasets
- One framework from data preparation to modeling

Cons:
- The algorithms need to be re-written for distributed computing
- No visualization natively present in Spark
- Different functionalities with different APIs (e.g. XGBoost only in Scala)
- Not necessarily faster

## Spark Data Structures and connection to Python

![Spark data structures](./image/spark_data_structures.PNG)

## Types of Parallelism

![Data and model parallelism](./image/parallelism.png)

[Resource](https://arxiv.org/pdf/1912.09789.pdf)

## ML Terminology (Spark, sklearn…)

Transformer:
- Input: DF → output: DF via **.transform()**
- Apply rule-based transformation, **no learning**
- Example: One-hot encoding, model

Estimator:
- **Learns** parameters via **.fit()** method
- Returns a model

Pipeline:
- Putting a series of transformers and estimators in a sequence
- **Automation**

## Steps of a Machine Learning project

- Dataset preparation (cleaning, feature engineering)
- Train/test (train/validation/test) split: 80/20 (60/20/20)
- Train the model (on the **train** data)
  - Cross-validation, leave-one-out
- Estimate the quality of the model (on the **validation** data)
- Tune the model to improve the performance
  - Grid search
- Test the final performance on the **test** data

![Steps of a ML project](./image/ml_steps.png)

## Linear Regression and Random Forest regression

![Linear regression and random forest](./image/linear_reg_rand_forest.png)
