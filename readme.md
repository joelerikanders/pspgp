# Predict Student Performance from Game Play Solution
This is the 4th place solution for the Kaggle competition [Predict Student Performance from Game Play](https://www.kaggle.com/competitions/predict-student-performance-from-game-play). Below you can find a outline of how to reproduce my solution, which is described in more detail in [this](https://www.kaggle.com/competitions/predict-student-performance-from-game-play/discussion/420349) post.

## CONTENTS
`models` : contains all trained models
`train.ipynb`:  code to rebuild models from scratch
`predict.ipynb` : code to generate new predictions
`prepare_data.ipynb` : code to parse the raw data

## HARDWARE
I used Google Colab Pro+
High-RAM mode (51 GB, 8 CPUs)
1 x T4 GPU

## DATA SETUP 
The Kaggle data can be dowloaded using the [Kaggle API](https://github.com/Kaggle/kaggle-api):
mkdir -p data
cd data
kaggle competitions download -c predict-student-performance-from-game-play -f train.csv
kaggle competitions download -c predict-student-performance-from-game-play -f train_labels.csv

The raw data was downloaded manually like this:
Download all (that's uploaded before 28-06-2023) "Events" raw data from [this](https://fielddaylab.wisc.edu/opengamedata/) site:
Unzip the downloaded folders and move their content to the top level in "data"

## DATA PROCESSING
Run all cells in prepare_data.ipynb

## TRAIN MODEL
Run all cells in train.ipynb.
Each model also produces predictions on the validation data, in respective folder.
The models folders all need to be empty, otherwise just validation predictions are produced.

## PREDICT
Run all cells in predict.ipynb, to perform predictons on data/test.csv 

## CONTACT
If you run into any trouble with the setup/code or have any questions please contact me at joel.erikanders@gmail.com
