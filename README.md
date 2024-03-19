# GWU-AI-Brackets-2024
# NCAA Basketball Score Prediction Model

This project aims to predict the score difference between two teams in an NCAA basketball game using a neural network model with embedding layers. The model is trained on historical game data and can be used to generate predictions for future matchups.

## Dataset

The model is trained on data from the `MRegularSeasonCompactResults.csv` file, which contains historical game results. The data is preprocessed to create team pairings and calculate the score difference for each game.

## Model Architecture

The model uses the following architecture:

- Input layers for team A and team B (label-encoded team IDs)
- Embedding layers for each team
- Flattening and concatenation of the embedding layers
- Dense layers with ReLU activation and dropout regularization
- Output layer with linear activation to predict the score difference

## Training

The model is trained using the Adam optimizer with a learning rate scheduler. The loss function used is mean squared error (MSE), and the model's performance is evaluated using mean absolute error (MAE).

## Usage

1. Ensure that you have the required dependencies installed (tensorflow, pandas, numpy, scikit-learn).
2. Prepare your dataset in the same format as `MRegularSeasonCompactResults.csv`.
3. Update the `curr_year` variable in the code to specify the year you want to use for training and predictions.
4. Run the script to train the model and generate predictions.
5. The trained model will be saved in the `bracket_model` directory, and the predictions will be saved in the `predictions.csv` file.

## Results

The model's accuracy is calculated based on the percentage of correctly predicted game outcomes (win or loss) on the test set. The accuracy is printed at the end of the script.

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
