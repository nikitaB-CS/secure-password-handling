# Case Study 6: Secure Password Handling (DevSecOps Intro)

## Objective
To understand secure coding practices and the importance of protecting sensitive information
such as passwords in source code repositories.

## Scenario
A student accidentally stores a database password inside a configuration file and pushes the
code to GitHub. This exposes the secret publicly and creates a security risk.

## Problem
Hardcoding passwords in source code can lead to:
- Credential leakage
- Unauthorized access
- Data breaches
- Compliance violations

Once a secret is pushed to GitHub, it should be considered compromised.

## Steps Performed

 Step 1: Insecure Implementation
A configuration file (`config.py`) contained a hardcoded password:
``python
DB_PASSWORD = "admin123"
Step 2: Code Pushed to GitHub

The file was committed and pushed to GitHub, making the secret publicly visible.

Step 3: Risk Identification

The risk of exposing sensitive credentials was identified and explained.

Step 4: Secure Fix Using .gitignore

A .gitignore file was created to prevent sensitive files from being committed:

config.py
.env

Step 5: Secure Password Handling

The hardcoded password was removed and replaced with an environment variable:

import os
DB_PASSWORD = os.getenv("DB_PASSWORD")
