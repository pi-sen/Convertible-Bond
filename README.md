# Convertible Bond Pricing with Soft Call Provision

## Description
This project implements pricing models for convertible bonds with n-out-of-m soft call provisions, based on the research paper "Back To the Future - An Approximate Solution for n out of m Soft-call Option" by Joshua Xingzhi Zhang.

## Table of Contents
- [Background](#background)
- [Implementation](#implementation)
- [Results](#results)
- [Dependencies](#dependencies)
- [Usage](#usage)
- [References](#references)

## Background
The project addresses the challenge of pricing convertible bonds with soft-call constraints that protect conversion privileges. The key aspects include:

- Soft-call requirement: Stock must close above a preset barrier for n out of m consecutive trading days
- Path-dependent feature making traditional pricing methods challenging
- Implementation of "Looking Backward" (LB) method for price approximation
- Use of auxiliary state variables to track barrier crossings

### Key Features
- Efficient computation compared to exact solutions
- Maximum error ~30 basis points for trinomial implementation
- Maximum error ~50 basis points for binomial implementation
- Extensible to general stock dynamics using PDE methods

## Implementation
The project consists of two main components:

### 1. Theoretical Model
- Auxiliary state variable approach
- Binomial tree implementation
- Barrier monitoring mechanism
- Price interpolation for non-node barriers

### 2. Machine Learning Models
Implemented and compared multiple approaches:
- Linear Regression
- Random Forest
- Gradient Boosting
- Neural Networks (MLPRegressor)
- TensorFlow Neural Network

## Results

### Model Performance Comparison
| Model | Training R² | Testing R² | Training RMSE | Testing RMSE | Overfitting |
|-------|------------|------------|---------------|--------------|-------------|
| Gradient Boosting | 1.0000 | 0.9998 | 0.0215 | 0.0761 | 0.0545 |
| Random Forest | 0.9999 | 0.9995 | 0.0366 | 0.1126 | 0.0760 |

### Selected Model: Gradient Boosting
Selected for superior performance in:
- Higher testing R² (0.9998)
- Lower testing RMSE (0.0761)
- Better generalization (overfitting margin: 0.0545)

## Dependencies
