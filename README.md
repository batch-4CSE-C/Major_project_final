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












