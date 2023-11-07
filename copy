def make_empty_board():
    return [
        [None, None, None],
        [None, None, None],
        [None, None, None],
    ]

def get_winner(board):
    for i in range(3):
        if board[i][0] == board[i][1] == board[i][2] and board[i][0] is not None:
            return board[i][0]
        if board[0][i] == board[1][i] == board[2][i] and board[0][i] is not None:
            return board[0][i]
    if board[0][0] == board[1][1] == board[2][2] and board[0][0] is not None:
        return board[0][0]
    if board[0][2] == board[1][1] == board[2][0] and board[0][2] is not None:
        return board[0][2]
    return None

def other_player(player):
    return "X" if player == "O" else "O"

def display_board(board):
    for row in board:
        print("|".join([cell or " " for cell in row]))
        print("-" * 5)

def take_turn(board, player):
    while True:
        move = input(f"{player}'s turn. Enter your move (row,col): ")
        try:
            row, col = map(int, move.split(","))
            if 0 <= row < 3 and 0 <= col < 3 and board[row][col] is None:
                board[row][col] = player
                return
            else:
                print("Invalid move. Try again.")
        except ValueError:
            print("Invalid input. Enter as row,col. Example: 1,2")

if __name__ == '__main__':
    board = make_empty_board()
    current_player = "X"
    winner = None

    while winner is None:
        display_board(board)
        take_turn(board, current_player)
        winner = get_winner(board)
        if winner is None:
            current_player = other_player(current_player)

    display_board(board)
    print(f"{winner} has won!")
