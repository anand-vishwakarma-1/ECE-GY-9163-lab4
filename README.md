# Backdoor Detector for BadNets on YouTube Face Dataset
Name: Anand Vishwakarma <br>
Net-ID: asv8775


Welcome to my GitHub repository for the backdoor detector project! In this assignment, I have implemented a backdoor detector for BadNets trained on the YouTube Face dataset using the pruning defense discussed in class.

## Project Overview

The goal of this project is to design a detector, denoted as G, which takes as input a backdoored neural network classifier (B) with N classes, along with a validation dataset of clean, labeled images (Dvalid). The detector outputs the correct class if the test input is clean (in the range [1, N]) and outputs class N+1 if the input is backdoored.

## Pruning Defense

To create G, I utilized the pruning defense discussed in class. The last pooling layer of BadNet B is pruned by removing one channel at a time in decreasing order of average activation values over the entire validation set. The pruning process continues until the validation accuracy drops at least X% below the original accuracy, resulting in the new network B'.

## Evaluation

I evaluated this defense on a BadNet, B1, with a "sunglasses backdoor" on YouTube Face, provided with validation and test data containing examples of clean and backdoored inputs. Additionally, I generated repaired networks for X={2%, 4%, 10%} and evaluated them.

## Repository Contents

- data directory should contain all the necessary data for the project. You can download the dataset from [here](https://drive.google.com/drive/folders/1Rs68uH8Xqa4j6UxG53wzD0uyI8347dSq)

## How to Run

1. Clone the repository
2. Download data from abovce link and place it data folder
3. Open [lab4.ipynb](lab4.ipynb) and run all the cells
4. Install the required dependencies if some modules are not installed in your env
      ```bash
      pip install -r requirements.txt
      ```

## Report

A [report](report.md) featuring a table with accuracy on clean test data and the attack success rate on backdoored test data as a function of the fraction of channels pruned (X).

Feel free to explore the code, provide feedback, and contribute to the project!
