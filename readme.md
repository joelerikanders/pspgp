# Predict Student Performance from Game Play Solution
This is the 4th place solution for the Kaggle competition [Predict Student Performance from Game Play](https://www.kaggle.com/competitions/predict-student-performance-from-game-play). Below you can find a outline of how to reproduce my solution, which is described in more detail in [this](https://www.kaggle.com/competitions/predict-student-performance-from-game-play/discussion/420349) post.

## Contents
- `models` : the trained models
- `train.ipynb`:  code to rebuild models from scratch
- `predict.ipynb` : code to generate new predictions
- `prepare_data.ipynb` : code to parse the raw data

## Hardware
- I used Google Colab Pro+
- High-RAM mode (51 GB, 8 CPUs)
- 1 x T4 GPU

## Data setup
The Kaggle data can be dowloaded using the [Kaggle API](https://github.com/Kaggle/kaggle-api)
1. mkdir -p data
2. cd data
3. kaggle competitions download -c predict-student-performance-from-game-play -f train.csv
4. kaggle competitions download -c predict-student-performance-from-game-play -f train_labels.csv

The raw data was downloaded manually like this:
1. Download all (that's uploaded before 28-06-2023) "Events" raw data from [this](https://fielddaylab.wisc.edu/opengamedata/) site
2. Unzip the downloaded folders and move their content to the top level in "data"

## Data processing
Run all cells in prepare_data.ipynb

## Train model
- Run all cells in train.ipynb.
- Each model also produces predictions on the validation data, in respective folder.
- The models folders all need to be empty, otherwise just validation predictions are produced.

## Predict
Run all cells in predict.ipynb, to perform predictions on data/test.csv 

## Contact
If you run into any trouble with the setup/code or have any questions please contact me at joel.erikanders@gmail.com
