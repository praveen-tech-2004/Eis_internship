# Credit Card Fraud Detection

## Overview
This repository contains a dataset used for detecting credit card fraud. The dataset includes transactions made by credit cards in September 2013 by European cardholders. This project aims to build a machine learning model to detect fraudulent transactions.

## Dataset Information

### Shape of the Dataset
- Original Dataset: (284807, 31)
- Filtered Dataset: (85442, 31)

### Columns
- **Time**: Number of seconds elapsed between this transaction and the first transaction in the dataset.
- **V1 to V28**: The result of a PCA transformation. These are the principal components obtained with PCA, which have anonymized the original features.
- **Amount**: Transaction amount.
- **Class**: Target variable (1: fraud, 0: not fraud).

### Sample Data
| Time | V1        | V2        | V3        | V4        | V5        | V6        | V7        | V8        | V9        | ... | V21       | V22       | V23       | V24       | V25       | V26       | V27       | V28       | Amount | Class |
|------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|--------|-------|
| 0.0  | -1.359807 | -0.072781 | 2.536347  | 1.378155  | -0.338321 | 0.462388  | 0.239599  | 0.098698  | 0.363787  | ... | -0.018307 | 0.277838  | -0.110474 | 0.066928  | 0.128539  | -0.189115 | 0.133558  | -0.021053 | 149.62 | 0     |
| 0.0  | 1.191857  | 0.266151  | 0.166480  | 0.448154  | 0.060018  | -0.082361 | -0.078803 | 0.085102  | -0.255425 | ... | -0.225775 | -0.638672 | 0.101288  | -0.339846 | 0.167170  | 0.125895  | -0.008983 | 0.014724  | 2.69   | 0     |
| 1.0  | -1.358354 | -1.340163 | 1.773209  | 0.379780  | -0.503198 | 1.800499  | 0.791461  | 0.247676  | -1.514654 | ... | 0.247998  | 0.771679  | 0.909412  | -0.689281 | -0.327642 | -0.139097 | -0.055353 | -0.059752 | 378.66 | 0     |
| 1.0  | -0.966272 | -0.185226 | 1.792993  | -0.863291 | -0.010309 | 1.247203  | 0.237609  | 0.377436  | -1.387024 | ... | -0.108300 | 0.005274  | -0.190321 | -1.175575 | 0.647376  | -0.221929 | 0.062723  | 0.061458  | 123.50 | 0     |
| 2.0  | -1.158233 | 0.877737  | 1.548718  | 0.403034  | -0.407193 | 0.095921  | 0.592941  | -0.270533 | 0.817739  | ... | -0.009431 | 0.798278  | -0.137458 | 0.141267  | -0.206010 | 0.502292  | 0.219422  | 0.215153  | 69.99  | 0     |

### Dataset Description
- **Outlier Fraction**: 0.15942606616181745%
- **Fraud Cases**: 136
- **Valid Transactions**: 85306

### Statistics of the Dataset

| Statistic | Time            | V1             | V2             | V3             | V4             | V5             | V6             | V7             | V8             | V9             | ... | V21            | V22            | V23            | V24            | V25            | V26            | V27            | V28            | Amount         | Class |
|-----------|-----------------|----------------|----------------|----------------|----------------|----------------|----------------|----------------|----------------|----------------|-----|----------------|----------------|----------------|----------------|----------------|----------------|----------------|----------------|----------------|-------|
| count     | 85442.000000    | 85442.000000   | 85442.000000   | 85442.000000   | 85442.000000   | 85442.000000   | 85442.000000   | 85442.000000   | 85442.000000   | 85442.000000   | ... | 85442.000000   | 85442.000000   | 85442.000000   | 85442.000000   | 85442.000000   | 85442.000000   | 85442.000000   | 85442.000000   | 85442.000000   | 85442.000000 |
| mean      | 94967.874862    | 0.003465       | 0.005440       | -0.004776      | 0.002485       | -0.001153      | 0.004429       | -0.006112      | 0.002718       | 0.000754       | ... | 0.000718       | 0.004176       | 0.000418       | 0.001474       | 0.000045       | -0.000012      | 0.000558       | -0.000118      | 87.034568      | 0.00159 |
| std       | 47520.526676    | 1.953426       | 1.611981       | 1.520529       | 1.413738       | 1.349284       | 1.319968       | 1.210313       | 1.208154       | 1.102415       | ... | 0.741520       | 0.726443       | 0.603298       | 0.605319       | 0.528998       | 0.499189       | 0.418200       | 0.371609       | 236.397065     | 0.0398 |
| min       | 0.000000        | -37.558067     | -48.060856     | -33.680984     | -5.600607      | -35.182120     | -20.869626     | -41.506796     | -50.420090     | -13.434066     | ... | -22.889347     | -8.887017      | -32.828995     | -2.824849      | -10.295397     | -2.725487      | -22.397267     | -15.393170     | 0.000000       | 0.0000 |
| 25%       | 54257.500000    | -0.918861      | -0.597627      | -0.898758      | -0.845937      | -0.696577      | -0.768914      | -0.559112      | -0.210279      | -0.645266      | ... | -0.390065      | -0.327808      | -0.182860      | -0.300739      | -0.317497      | -0.354350      | -0.344156      | -0.334589      | 5.600000       | 0.0000 |
| 50%       | 84962.000000    | 0.027558       | 0.063774       | 0.172342       | -0.015543      | -0.049751      | -0.274150      | 0.033633       | 0.022630       | -0.052660      | ... | -0.054337      | -0.005993      | -0.000197      | -0.005714      | -0.000261      | -0.000030      | -0.000593      | -0.000198      | 22.000000      | 0.0000 |
|
