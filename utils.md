### Utils Function Description

### Function: get_game_result
Input: A chess.pgn.Game object and a chess.Color (either chess.WHITE or chess.BLACK).
Output: -1 for a draw, 1 if the color won, 0 if the color lost.
What it does: Extracts the game result from the PGN header and returns the outcome based on the given color.

### Function: get_piece_value
Input: A chess.Board and a chess.Color (either chess.WHITE or chess.BLACK).
Output: Total piece value for the given color.
What it does: Sums up the values of pieces on the board for the specified color using predefined piece values.

### Function: get_piece_position_value
Input: A chess.Piece, its position (i, j), the current moveNum, and a limit.
Output: A numerical value indicating the piece's positional strength.
What it does: Calculates the positional strength of a piece based on its type, position, and game phase (early or late).

### Function: get_board_position_value
Input: A chess.Board, a chess.Color, and a limit for the game phase.
Output: The average positional strength of all pieces for the given color.
What it does: Computes the average positional strength for all pieces of the given color on the board.

### Function: board_to_vec
Input: A chess.Board.
Output: A 1D NumPy array (length 64) representing the board's piece placement.
What it does: Converts the board to a vector where each square's value corresponds to a piece type (positive for white, negative for black).

### Function: game_to_vec
Input: A chess.pgn.Game and moves_limit.
Output: A concatenated 1D NumPy array of board states for each move, up to moves_limit.
What it does: Converts the game into a sequence of board vectors, each representing a move in the game.

Function: game_to_movetext
Input: A chess.pgn.Game and an optional move_limit.
Output: A list of move strings in Standard Algebraic Notation (SAN).
What it does: Converts the game into a list of moves in SAN, limited by move_limit.

