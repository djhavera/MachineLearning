# Customer Segmentation Using Unsupervised Learning

This repository contains a project that utilizes unsupervised learning techniques to analyze and understand customer segmentation based on annual spending amounts across different categories. The goal is to provide a wholesale distributor with insights into how to structure their delivery service to meet the needs of each customer.

## Table of Contents

1. [Project Overview](#project-overview)
2. [Data Description](#data-description)
3. [Methodology](#methodology)
   - [Feature Relevance Analysis](#feature-relevance-analysis)
   - [Feature Scaling](#feature-scaling)
   - [Outlier Detection](#outlier-detection)
   - [Principal Component Analysis (PCA)](#principal-component-analysis)
4. [Results](#results)
5. [Tools and Libraries](#tools-and-libraries)
6. [Getting Started](#getting-started)
7. [Acknowledgments](#acknowledgments)

## Project Overview

The project aims to analyze a dataset containing data on various customers' annual spending amounts (reported in monetary units) across diverse product categories. The primary goal is to best describe the variation in the different types of customers that a wholesale distributor interacts with. By segmenting customers, the distributor can optimize their delivery services according to the specific needs of each segment.

## Data Description

The customer segments data is included as a selection of 440 data points collected on data found from clients of a wholesale distributor in Lisbon, Portugal. More information can be found on the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Wholesale+customers).

Note (m.u.) is shorthand for _monetary units_.

**Features**

1. `Fresh`: annual spending (m.u.) on fresh products (Continuous);
2. `Milk`: annual spending (m.u.) on milk products (Continuous);
3. `Grocery`: annual spending (m.u.) on grocery products (Continuous);
4. `Frozen`: annual spending (m.u.) on frozen products (Continuous);
5. `Detergents_Paper`: annual spending (m.u.) on detergents and paper products (Continuous);
6. `Delicatessen`: annual spending (m.u.) on and delicatessen products (Continuous);
7. `Channel`: {Hotel/Restaurant/Cafe - 1, Retail - 2} (Nominal)
8. `Region`: {Lisbon - 1, Oporto - 2, or Other - 3} (Nominal)

## Methodology

### Feature Relevance Analysis

In this section, we attempt to predict one feature using others. By determining the relevance of different features, we can understand their relationship and significance in customer segmentation.

### Feature Scaling

As the data is not normally distributed, we apply non-linear scaling to normalize the data. This is essential, especially for financial data, to ensure that the model is not influenced by the scale of different features.

### Outlier Detection

This section is dedicated to detecting and handling outliers in the dataset. The presence of outliers can skew the results, and thus we use Tukey's Method for identifying them.

### Principal Component Analysis (PCA)

PCA is used to reduce the dimensionality of the data by creating new features that maximize the variance of the data. These features are combinations of the original features present in the data.

## Results

The results section describes the customer segments that were discovered through the unsupervised learning process. It involves visualizations and interpretations of the principal components in terms of customer spending.

## Tools and Libraries

- Python
- NumPy
- pandas
- scikit-learn
- matplotlib
- seaborn

## Getting Started

Instructions on how to set up your project locally.

1. Clone the repository
2. Install the required libraries
3. Run the Jupyter Notebook

## Acknowledgments

- Udacity
