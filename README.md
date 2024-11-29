Feature Extraction Functions Description

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
5	-                3	            2	          -1	           7 	       18	     -8	     6	     -3	      20	   190.2	        2	     0

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

### get_short_features(games, games_limit, moves_limit)
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









