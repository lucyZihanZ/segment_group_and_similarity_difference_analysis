# Distance and Similarity Matrix Calculation Script

## Overview
This script calculates `distance and similarity matrices` for users based on their demographic and interest data extracted from multiple sheets in an Excel file. 
The purpose is to analyze the *relationships* between different user profiles using various information like sex, age, city, and interests.

## Key Features
- **Euclidean Distance Calculation**: Used to compute the distance between different user profiles.
- **Similarity Calculation**: Defined as the inverse of (1 + Euclidean distance), providing a similarity measure between users.
- **Profile Data Compilation**: Data for sex, age, city, and interests are compiled from multiple sheets in the Excel file.
- **Data Standardization**: Interest data is standardized to bring different features to the same scale for more accurate similarity and distance calculations.
- **Distance and Similarity Matrices**: Calculated for different aspects of user profiles:
  - **User Attributes**: Sex, Age, City.
  - **Interests**: Interest data for different categories.
  - **Combined Attributes and Interests**: Overall user profiles.

## Functions and Methods
- **`dist(a, b)`**: Computes the Euclidean distance between two vectors `a` and `b`.
- **`simi(a, b)`**: Computes the similarity between two vectors `a` and `b` based on the Euclidean distance.

## Workflow
1. **Data Extraction**: Extracts data from the Excel file for each attribute:
   - Sex, Age, City, Interests.
2. **Standardization**: Standardizes the interest data for better analysis.
3. **Profile Combination**: Combines the different attributes and interest data for each user.
4. **Distance & Similarity Matrices**: Computes matrices for user attributes, interests, and the combined profile:
   - `distMatrix_user`, `simiMatrix_user`: Matrices for user attributes.
   - `distMatrix_intrest`, `simiMatrix_intrest`: Matrices for user interests.
   - `distMatrix_all`, `simiMatrix_all`: Matrices for the entire user profile.

## Usage
The function `get_dist_and_simi(path, sexRow, ageRow, cityRow, intrestRow, intrestNum)` can be called with the following parameters:
- **`path`**: Path to the Excel file containing user data.
- **`sexRow`**: Row index for the sex attribute data.
- **`ageRow`**: Row index for the age attribute data.
- **`cityRow`**: Row index for the city attribute data.
- **`intrestRow`**: Starting row index for interest data.
- **`intrestNum`**: Number of rows for interest data.

The function returns six matrices:
- **User Distance Matrix** (`distMatrix_user`)
- **User Similarity Matrix** (`simiMatrix_user`)
- **Interest Distance Matrix** (`distMatrix_intrest`)
- **Interest Similarity Matrix** (`simiMatrix_intrest`)
- **Total Distance Matrix** (`distMatrix_all`)
- **Total Similarity Matrix** (`simiMatrix_all`)

## Packages Usage
- **Pandas** (`import pandas as pd`)
- **Math** (`import math`)
