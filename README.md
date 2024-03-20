# Team Name: Cool
# Team Member: Jiaye(Oscar) Fang, G42568236, oscar.fang@gwu.edu
# George Washington University, Master of Data Analytics

# GWU-AI-Brackets-2024
# NCAA Basketball Score Prediction Model

This project aims to predict the score difference between two teams in an NCAA basketball game using a neural network model with embedding layers. The model is trained on historical game data and can be used to generate predictions for future matchups.

# NCAA March Madness Bracket Predictor

This project aims to predict the winners of matches in the NCAA March Madness tournament using a machine learning model. The model is trained on historical game data and uses team rankings and other features to make predictions.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Data](#data)
- [Model](#model)
- [Functions](#functions)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)

## Installation

To install the required packages, run the following command:

"""
pip install -r requirements.txt
"""

Make sure you have Python 3.x installed on your system.

## Usage

1. Clone the repository:
   
"""
git clone https://github.com/your-username/ncaa-bracket-predictor.git
"""

2. Install the required packages as mentioned in the [Installation](#installation) section.

3. Run the Jupyter Notebook or Python script to train the model and generate predictions.

4. Use the provided functions to find the winner of a specific match between two teams.

## Data

The model is trained on data from the `MRegularSeasonCompactResults.csv` file, which contains historical game results. The data is preprocessed to create team pairings and calculate the score difference for each game.

The project uses the following datasets:

- `MRegularSeasonCompactResults.csv`: Historical game data for regular season matches.
- `MTeams.csv`: Information about the teams participating in the tournament.

The datasets are stored in the `/kaggle/input/` directory.

## Model

The project uses a neural network model implemented with TensorFlow and Keras. The model architecture consists of embedding layers for team representations, followed by dense layers and dropout for regularization.

The model is trained on historical game data, using team rankings and other features to predict the winner of each match.

## Model Architecture

The model uses the following architecture:

- Input layers for team A and team B (label-encoded team IDs)
- Embedding layers for each team
- Flattening and concatenation of the embedding layers
- Dense layers with ReLU activation and dropout regularization
- Output layer with linear activation to predict the score difference

# NCAA Basketball Prediction Model

This repository contains my neural network model for predicting the outcomes of NCAA basketball games based on historical data.

## Differences from the Sample Model

After reviewing the sample model provided, I have identified several key differences between my model and the sample model:

1. Data Preprocessing:
   - The sample model utilizes a `convert_wl_to_ab` function to convert the win/loss team format to a team A/B format. In contrast, my model directly uses the team names without any conversion.
   - While the sample model calculates the score difference between team A and team B, I have chosen not to include this step in my preprocessing pipeline.

2. Model Architecture:
   - I have opted for a simpler architecture compared to the sample model. My model consists of embedding layers for the team names, followed by a concatenation layer and a single dense layer.
   - The sample model incorporates additional dense layers with dropout regularization, which I have not included in my model.

3. Hyperparameters:
   - In my model, I have set the embedding dimension to a fixed value of 32 and the batch size to 25 for training. The sample model defines these as hyperparameters that can be easily adjusted.
   - The sample model includes a dropout rate hyperparameter, which I have not incorporated into my model.

4. Training:
   - I have chosen to train my model for 10 epochs, while the sample model is trained for 20 epochs.
   - The sample model employs a learning rate scheduler callback during training, which I have not implemented in my model.

5. Model Evaluation:
   - Both my model and the sample model calculate the accuracy of predictions by comparing the predicted score differences with the actual score differences.
   - However, the sample model provides additional evaluation metrics such as mean squared error (MSE) and mean absolute error (MAE), which I have not included in my evaluation process.

6. Generating Predictions:
   - Like the sample model, my model generates predictions for all possible team pairings in the current year's tournament.
   - While the sample model uses the `np.where` function to determine the predicted winner based on the score difference, I have chosen to directly use the predicted score difference in my model.

7. Saving the Model:
   - Both models save the trained model for future use.
   - The sample model saves the model with the `.keras` extension, while I have saved my model without any specific extension.

In summary, my model shares some similarities with the sample model but differs in terms of architecture simplicity, preprocessing steps, hyperparameter settings, training duration, evaluation metrics, and model saving format. I acknowledge that the performance and effectiveness of my model may vary compared to the sample model, and I am open to experimenting with different approaches to further improve my model's predictive capabilities.

## Training

The model is trained using the Adam optimizer with a learning rate scheduler. The loss function used is mean squared error (MSE), and the model's performance is evaluated using mean absolute error (MAE).

## Functions

The project provides the following function:

- `find_match_winner(team_pairs_df, team_a, team_b)`: Finds the winner of a match between two specified teams based on the predicted results.

## Results

The trained model achieves an accuracy of around 66% in predicting the winners of matches.

The predicted results are saved in the `predictions.csv` and `predictions(name).csv` files.

## Contributing

Contributions to the project are welcome. If you find any issues or have suggestions for improvements, please open an issue or submit a pull request.

## Future Improvements

- Experiment with different model architectures and hyperparameters to improve performance.
- Incorporate additional features, such as team rankings, player statistics, or home/away information.
- Use more advanced techniques like cross-validation and hyperparameter tuning to optimize the model.
- Explore other machine learning algorithms and compare their performance.

## License

This project is licensed under the [MIT License](LICENSE).

## Acknowledgments

- The dataset used in this project is sourced from [Kaggle](https://www.kaggle.com/c/mens-march-mania-2021).
- The model architecture is inspired by various examples and tutorials on embedding layers and sports prediction.
