# Tic-Tac-Toe-Game-
python code for the game
board = [" " for i in range(9)]         # board
def print_board():       # board structure
    row1 = "|{}|   |{}|   |{}|".format(board[0],board[1],board[2])
    row2 = "|{}|   |{}|   |{}|".format(board[3], board[4], board[5])
    row3 = "|{}|   |{}|   |{}|".format(board[6], board[7], board[8])
    print()
    print(row1)
    print(row2)
    print(row3)
    print()

def player_move(icon):
    if icon == "X":
        number = "player1"
    else:
        number = "player2"
    print("the turn of {}".format(number))
    choice = int(input("Give the number between(1-9): ").strip())
    if board[choice - 1] == " ":
        board[choice - 1] = icon
    else:
        print()
        print("that space is taken!!!")
def is_win(icon):
    if  (board[0]==icon and board[1]==icon and board[2]==icon ) or\
        (board[3] == icon and board[4] == icon and board[5] == icon) or\
        (board[6] == icon and board[7] == icon and board[8] == icon) or\
        (board[0] == icon and board[5] == icon and board[8] == icon) or \
        (board[2] == icon and board[5] == icon and board[7] == icon) :
        return True
    else:
        return False

def is_draw():
    if " " not in board :
        return True
    else:
      return False


while True:
    print_board()
    player_move("X")
    print_board()
    if is_win("X"):
        print("Player1 is the winner")
        break
    if is_draw():
        print("you both are boss")
        break
    player_move("O")
    if is_win("O"):
        print("player2 is the winner")
        break
    if is_draw():
        print("you both are boss")
        break

