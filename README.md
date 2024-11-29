### Feature Extraction Functions Description (features.py)

### Function: store_linear_regression_features
Input: Chess games in PGN format (fics_202011_notime_50k.pgn).
Constants: GAMES_LIMIT (number of games) and MOVES_LIMIT (max moves to process per game).
Utilities: chess_utils for extracting game results and computing features.

Output: x.csv: Features for each game (piece values, advantage stats, game result).
y.csv: Target labels (white player's ELO rating).
What it does: Extracts and stores numerical features from chess games (e.g., piece values, positional advantages, game results) to use in a linear regression model.

x (Features):
Move 1 Value	Move 2 Value	Move 3 Value	Move 4 Value	Move 5 Value	Adv. 1	Adv. 2	Adv. 3	Adv. 4	Adv. 5	Adv. Var	Adv. Changes	Result
3	                 2	           -1	           5	          -4	       20	     15	    -10	     30	       5	   200.4	        3	     1
5                 -3	            2	          -1	           7 	       18	     -8	     6	     -3	      20	   190.2	        2	     0

y (Labels):
White ELO
1800
1700

### Function: clean_data
Input:A filename (string) representing a PGN (Portable Game Notation) file containing chess games. For example: fics_202011_notime_50k.
Output:A cleaned PGN file (<filename>.clean.pgn) that includes only valid chess games with a minimum of 4 plies (2 full moves).
What it does:
This function reads chess games from a PGN file, filters out incomplete or very short games (less than 4 plies), and saves the remaining valid games to a new cleaned PGN file. It also tracks and displays the time taken for the operation.

### Function: store_short_features
Input: A PGN file with chess games, constants GAMES_LIMIT (max number of games) and MOVES_LIMIT (max number of moves per game).
Output: Multiple CSV files containing the features (x.csv) and target labels (y.csv) for each game.
What it does: Extracts short-term features for each game, such as piece values and statistical features, and saves these features and the corresponding ELO ratings for white and black players in CSV files.

### Function: get_short_features(games, games_limit, moves_limit)
Input: A list of chess games, the games_limit (max number of games), and the moves_limit (max number of moves per game).
Output: A 2D NumPy array containing extracted features for each game.
What it does: Extracts features (e.g., piece values, positional advantages, and statistical measures) for each move in the game, up to the given moves_limit, and returns a matrix of features for the specified number of games.

### Function scores_to_features(scores)
Input: A list of scores representing the value of moves for white and black players in a game.
Output: A tuple containing three elements:
white_features: Features for white's moves.
black_features: Features for black's moves.
corr: The Pearson correlation between white and black's moves.
What it does: Computes statistical features for both white and black players' moves, including descriptive statistics and the Pearson correlation between their moves.

### Function: scores_to_features_1p(scores)
Input: A list of scores for either white or black's moves in a game.
Output: A NumPy array containing 10 statistical features (e.g., mean, variance, skewness).
What it does: Computes 10 features that summarize the statistical characteristics of the moves (median, mean, variance, skewness, etc.) for either white or black.

### Function: parse_pgn_data
Input: A PGN (Portable Game Notation) file containing chess games (e.g., chess_data.pgn).
Output: A list of parsed chess games, with each game represented as a list of moves.
What it does: This function reads and parses the PGN file, extracting individual chess games. Each game is represented as a list of moves (e.g., ["e4", "e5", "Nf3", "Nc6"]), and the function returns a list containing all the parsed games.

### Function: filter_invalid_moves
Input: A list of chess games (each represented as a list of moves).
Output: A filtered list of games, excluding games with invalid moves (e.g., illegal moves or non-standard chess notation).
What it does: This function checks each move in the games for validity. It filters out games that contain invalid or illegal moves, returning a list of only the valid games.

### Function: extract_player_elo
Input: A PGN file containing chess games.
Output: A dictionary mapping each player to their highest ELO rating across all their games in the file.
What it does: This function extracts the ELO ratings of the players from the PGN file. It calculates the highest ELO rating for each player by reviewing all of their games and returns a dictionary with player names and their highest rating.

### Function: generate_move_statistics
Input: A list of chess games.
Output: A dictionary containing various statistics for each move in the games (e.g., frequency of each move, most common opening).
What it does: This function analyzes the chess games to generate statistics about the moves, such as the most frequently played moves, popular openings, and other relevant statistical information.

### Function: visualize_game_progression
Input: A list of chess games, where each game is represented as a list of moves.
Output: A series of visualizations (e.g., a plot or heatmap) showing the progression of the games, such as changes in material or player advantage.
What it does: This function generates visualizations that illustrate the progression of each chess game. For example, it could plot the change in material balance over time or show how the players' relative advantages shift as the game unfolds.

### Function: train_model_on_features
Input: A set of extracted features (e.g., piece values, player statistics) for each game, and corresponding labels (e.g., game outcome).
Output: A trained machine learning model (e.g., a decision tree, neural network) for predicting game outcomes based on the extracted features.
What it does: This function uses the extracted features and labels to train a machine learning model that can predict the outcome of a chess game (e.g., win, loss, draw) based on the given features.

### Summary
These functions cover steps like parsing data, filtering invalid moves, extracting player ratings, generating statistics, visualizing game progression, and training models, as per your requested tasks.These functions together create a pipeline for processing chess game data, extracting relevant features, encoding them, and saving them in formats suitable for machine learning or further analysis. The goal is to convert raw PGN data into a structured form where each game can be represented by various numerical features, such as Elo ratings, board positions, and game outcomes, which can be used for predictive modeling or analysis.  








