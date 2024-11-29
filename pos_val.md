Data Structure: piece_weights_cp
Values: Piece values in centipawns for pawn, knight, bishop, rook, queen, and king.
What it does: Stores piece values to evaluate the material strength of a position.

Array: pawn_weights_w
Shape: 8x8 matrix
What it does: Defines the positional value of pawns for white. It represents how each square on the board affects a pawn's strength.

Array: pawn_weights_b
Shape: 8x8 matrix
What it does: Defines the positional value of pawns for black. It’s a flipped version of pawn_weights_w.

Array: knight_weights_w
Shape: 8x8 matrix
What it does: Defines the positional value of knights for white, considering board control and potential moves.

Array: knight_weights_b
Shape: 8x8 matrix
What it does: Defines the positional value of knights for black, flipped version of knight_weights_w.

Array: bishop_weights_w
Shape: 8x8 matrix
What it does: Defines the positional value of bishops for white. It evaluates the influence of bishops based on their position.

Array: bishop_weights_b
Shape: 8x8 matrix
What it does: Defines the positional value of bishops for black, flipped version of bishop_weights_w.

Array: rook_weights_w
Shape: 8x8 matrix
What it does: Defines the positional value of rooks for white, focusing on control of open files and board influence.

Array: rook_weights_b
Shape: 8x8 matrix
What it does: Defines the positional value of rooks for black, flipped version of rook_weights_w.

Array: queen_weights_w
Shape: 8x8 matrix
What it does: Defines the positional value of queens for white. It evaluates the queen's influence and centralization.

Array: queen_weights_b
Shape: 8x8 matrix
What it does: Defines the positional value of queens for black, flipped version of queen_weights_w.

Array: king_weights_mid_w
Shape: 8x8 matrix
What it does: Defines the positional value of the king in the middle game for white, prioritizing safety and centralization.

Array: king_weights_mid_b
Shape: 8x8 matrix
What it does: Defines the positional value of the king in the middle game for black, flipped version of king_weights_mid_w.

Array: king_weights_late_w
Shape: 8x8 matrix
What it does: Defines the positional value of the king in the endgame for white, emphasizing safety and mobility.

Array: king_weights_late_b
Shape: 8x8 matrix
What it does: Defines the positional value of the king in the endgame for black, flipped version of king_weights_late_w.

List: weights_w
Elements: Arrays for each piece (pawn, knight, bishop, rook, queen, king in middle and late game) for white.
What it does: Collects the positional weights for all white pieces.

List: weights_b
Elements: Arrays for each piece (pawn, knight, bishop, rook, queen, king in middle and late game) for black.
What it does: Collects the positional weights for all black pieces.

