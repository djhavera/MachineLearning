# Supervised Learning

## Project: Finding Donors for CharityML

### Introduction

CharityML is a fictitious charity organization located in the heart of Silicon Valley that was established to provide financial support for people eager to learn machine learning. In this project, you will employ several supervised algorithms to accurately model individuals' income using data collected from the 1994 U.S. Census. You will then choose the best candidate algorithm from preliminary results and further optimize this algorithm to best model the data. Your goal with this implementation is to construct a model that accurately predicts whether an individual makes more than $50,000. This sort of task can arise in a non-profit setting, where organizations survive on donations. Understanding an individual's income can help a non-profit better understand how large of a donation to request, or whether or not they should reach out to begin with.

### Install

This project requires **Python 3.8** and the following Python libraries installed:

- [NumPy](http://www.numpy.org/)
- [Pandas](http://pandas.pydata.org)
- [matplotlib](http://matplotlib.org/)
- [scikit-learn](http://scikit-learn.org/stable/)

You will also need to have software installed to run and execute a [Jupyter Notebook](http://jupyter.org/index.html).

We recommend installing [Anaconda](https://www.anaconda.com/distribution/), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project.

### Code

Template code is provided in the `finding_donors.ipynb` notebook file. You will also be required to use the included `visuals.py` Python file and the `census.csv` dataset file to complete your work. While some code has already been implemented to get you started, you will need to implement additional functionality when requested to successfully complete the project. Note that the code included in `visuals.py` is meant to be used out-of-the-box and not intended for students to manipulate. If you are interested in how the visualizations are created in the notebook, please feel free to explore this Python file.

### Run

In a terminal or command window, navigate to the top-level project directory `finding_donors/` (that contains this README) and run one of the following commands:

```sh
jupyter notebook finding_donors.ipynb
```

### Data

The modified census dataset consists of approximately 32,000 data points, with each data point having 13 features. This dataset is a modified version of the dataset published in the paper _"Scaling Up the Accuracy of Naive-Bayes Classifiers: a Decision-Tree Hybrid"_, by Ron Kohavi. You may find this paper [online](https://www.aaai.org/Papers/KDD/1996/KDD96-033.pdf), with the original dataset hosted on [UCI](https://archive.ics.uci.edu/ml/datasets/Census+Income).

**Features**

- `age`: Age
- `workclass`: Working Class (Private, Self-emp-not-inc, Self-emp-inc, Federal-gov, Local-gov, State-gov, Without-pay, Never-worked)
- `education_level`: Level of Education (Bachelors, Some-college, 11th, HS-grad, Prof-school, Assoc-acdm, Assoc-voc, 9th, 7th-8th, 12th, Masters, 1st-4th, 10th, Doctorate, 5th-6th, Preschool)
- `education-num`: Number of educational years completed
- `marital-status`: Marital status (Married-civ-spouse, Divorced, Never-married, Separated, Widowed, Married-spouse-absent, Married-AF-spouse)
- `occupation`: Work Occupation (Tech-support, Craft-repair, Other-service, Sales, Exec-managerial, Prof-specialty, Handlers-cleaners, Machine-op-inspct, Adm-clerical, Farming-fishing, Transport-moving, Priv-house-serv, Protective-serv, Armed-Forces)
- `relationship`: Relationship Status (Wife, Own-child, Husband, Not-in-family, Other-relative, Unmarried)
- `race`: Race (White, Asian-Pac-Islander, Amer-Indian-Eskimo, Other, Black)
- `sex`: Sex (Female, Male)
- `capital-gain`: Monetary Capital Gains
- `capital-loss`: Monetary Capital Losses
- `hours-per-week`: Average Hours Per Week Worked
- `native-country`: Native Country (United-States, Cambodia, England, Puerto-Rico, Canada, Germany, Outlying-US(Guam-USVI-etc), India, Japan, Greece, South, China, Cuba, Iran, Honduras, Philippines, Italy, Poland, Jamaica, Vietnam, Mexico, Portugal, Ireland, France, Dominican-Republic, Laos, Ecuador, Taiwan, Haiti, Columbia, Hungary, Guatemala, Nicaragua, Scotland, Thailand, Yugoslavia, El-Salvador, Trinadad&Tobago, Peru, Hong, Holand-Netherlands)

**Target Variable**

- `income`: Income Class (<=50K, >50K)

### Model Application

I will test these models in this project:

1. **Naive Bayes (NB)**

   - **Real-world application**: To classify email as spam or not spam
   - **Model strengths and when it performs well**:
     - Good Performance: With discrete data and when attributes are conditionally independent.
     - Prediction is based on information from many attributes.
     - NB is fast and has short training times.
     - It is robust to irrelevant attributes.
   - **Model weaknesses and when it performs poorly**:
     - Poor Performance: With incomplete training data, continuous variables, and attribute interdependence.
     - It relies on an often-faulty assumption of equally important and independent features.
   - **What makes this model a good candidate for the problem, given what you know about the data?**
     - Naive Bayes is easy to implement and can be efficient with many features. It is worth trying given that we have a large dataset.

2. **Decision Trees (DT)**

   - **Real-world application**: Credit scoring in financial analysis.
   - **Model strengths and when it performs well**:
     - Good Performance: On data that can be hierarchically divided.
     - It handles both categorical and numerical data.
     - It's easy to interpret the output.
   - **Model weaknesses and when it performs poorly**:
     - Poor Performance: With data that can't be split hierarchically.
     - It tends to overfit.
   - **What makes this model a good candidate for the problem, given what you know about the data?**
     - Our dataset has hierarchical features, and Decision Trees will be able to derive structure from these.

3. **Support Vector Machines (SVM)**
   - **Real-world application**: Image recognition, text classification.
   - **Model strengths and when it performs well**:
     - Good Performance: When there's a clear margin of separation in data.
     - It is effective in high-dimensional spaces.
     - It works well when there is a clear margin of separation.
   - **Model weaknesses and when it performs poorly**:
     - Poor Performance: With large datasets and overlapping classes.
     - It has long training times on large datasets.
   - **What makes this model a good candidate for the problem, given what you know about the data?**
     - Our data might have a clear margin of separation for income levels and SVMs can capture complex relationships.
