# IPL Win Prediction Project
https://ipl-win-prediction-project.streamlit.app/

## Overview
This project aims to predict the outcome of IPL matches using machine learning techniques. The model analyzes various match features, team performance, and player statistics to provide real-time predictions.

## Project Structure
- `app.py`: Main application file.
- `data.ipynb`: Jupyter notebook for data analysis.
- `model.py`: Script for building and training the prediction model.
- `dataset.csv`: Dataset used for training the model.
- `requirements.txt`: List of dependencies required to run the project.

## Installation
1. Clone the repository:
    ```bash
    git clone https://github.com/harsh09tiwari/IPL-Win-Prediction-Project.git
    ```
2. Navigate to the project directory:
    ```bash
    cd IPL-win-prediction-project
    ```
3. Install the required packages:
    ```bash
    pip install -r requirements.txt
    ```

## Usage
1. Run the application:
    ```bash
    streamlit run app.py
    ```
2. Open your browser and go to `http://localhost:5000` to access the application.

## Contributing
Feel free to fork this repository and submit pull requests. For major changes, please open an issue first to discuss what you would like to change.

## License
This project is licensed under the MIT License.


## Data Loading
The code loads data from two CSV files, `matches.csv` and `deliveries.csv`, into two DataFrames, `matches` and `deliveries`, respectively.

## Data Preprocessing
The code performs various data preprocessing tasks, such as:
- Merging the `matches` and `deliveries` DataFrames based on the `match_id` column.
- Filtering the data to only include matches where the `dl_applied` column is 0.
- Selecting only the required columns from the merged DataFrame.
- Renaming some columns for better understanding.

## Feature Engineering
The code creates new features, such as:
- `current_score`: The cumulative sum of the `total_runs_y` column.
- `runs_left`: The difference between the `total_runs_x` column and the `current_score` column.
- `balls_left`: The difference between 126 (the total number of balls in an innings) and the product of the `over` column and 6 plus the `ball` column.
- `wickets`: The difference between 10 (the total number of wickets in an innings) and the cumulative sum of the `player_dismissed` column.
- `crr`: The current run rate, calculated as the `current_score` column divided by the `balls_left` column, multiplied by 6.
- `rrr`: The required run rate, calculated as the `runs_left` column divided by the `balls_left` column, multiplied by 6.

## Model Building
The code builds a logistic regression model using the `LogisticRegression` class from the `sklearn.linear_model` module. The model is trained on the preprocessed data.

## Model Evaluation
The code evaluates the performance of the model using the `accuracy_score` function from the `sklearn.metrics` module.

## Model Prediction
The code uses the trained model to make predictions on the test data.

## Data Visualization
The code creates a line plot to visualize the progression of the match, including the number of wickets taken, runs scored, and the win and loss probabilities.
