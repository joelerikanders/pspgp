Below you can find a outline of how to reproduce my solution for the Predict Student Performance from Game Play competition.
If you run into any trouble with the setup/code or have any questions please contact me at joel.erikanders@gmail.com

## ARCHIVE CONTENTS
xgb_models : XGBoost models and auxiliary files
cat_models : Catboost models and auxiliary files
torch_models : Transformer models and auxiliary files
meta_models : Linear regression models and auxilliary files
train.ipynb : code to rebuild models from scratch
predict.ipynb : code to generate predictions from model binaries
raw_data_parser.ipynb : code to parse the raw data

## HARDWARE
I used Google Colab Pro+
High-RAM mode (51 GB, 8 CPUs)
1 x T4 GPU

## DATA SETUP (assumes the [Kaggle API](https://github.com/Kaggle/kaggle-api) is installed)
mkdir -p data
cd data
kaggle competitions download -c predict-student-performance-from-game-play -f train.csv
kaggle competitions download -c predict-student-performance-from-game-play -f train_labels.csv

The raw data was downloaded manually like this:
Download all (uploaded before competition end) "Events" raw data from the site:
https://fielddaylab.wisc.edu/opengamedata/
Unzip the downloaded folders and move their content to the top level in "data"

## DATA PROCESSING
Run all cells in raw_data_parser.ipynb

## TRAIN MODEL
Run all cells in train.ipynb.
To train the simplified model described under A7 in the model_summary, set ONLY_TR_FEATURES=True in the 7th cell. 
The models folders all need to be empty.
Each model also produces oof predictions, in respective folder.

## PREDICT
Run all cells in predict.ipynb, to perform predictons on data/test.csv 
To predict using the simplified model described under A7 in the model_summary, set ONLY_TR_FEATURES=True in the 5th cell. 
