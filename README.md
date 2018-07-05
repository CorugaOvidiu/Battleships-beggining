# Battleships-beggining
Using the knowledge gathered in 1 week of learning python i created this program based on the idea from codecademy

### BATTLESHIPS PART 1 ###

from random import randint

board = []

for x in range(5):
  board.append(["O"] * 5)

def print_board(board):
  for row in board:
    print " ".join(row)

print_board(board)

def random_row(board):
  return randint(0, len(board) - 1)

def random_col(board):
from random import randint
choice=raw_input("Welcome to Battleships!. Write 'yes,'Yes' or 'y' to start and press 'Enter'.")
def game(choice):
    
    board = []
  
    for x in range(5):
      board.append(["O"] * 5)
  
    
  
    def print_board(board):
      for row in board:
        print " ".join(row)
  
    
    print_board(board)
  
    
    def random_row(board):
      return randint(0, len(board) - 1)
  
   
    def random_col(board):
      return randint(0, len(board[0]) - 1)
  
    
    ship_row = random_row(board)
    ship_col = random_col(board)
    ship_row2 = random_row(board)
    ship_col2 = random_col(board)
    
    if ship_row == ship_row2 and ship_col == ship_col2:
      ship_row2=random_row(board)
      ship_col2=random_col(board)
  
    
    print "Ship 1 : %s / %s" % (ship_row,ship_col)
    print "Ship 2 : %s / %s" % (ship_row2,ship_col2)
    
    print "Pick coordonates.(The coordonates are between 0 and 4 and you have only 5 tries.)"
   
    for turn in range(5):
      
          print "Turn", turn + 1
          guess_row = int(raw_input("Pick row and press Enter:  "))
          guess_col = int(raw_input("Pick col and press Enter:  "))
                
          
          
          if (guess_row < 0 or guess_row > 4) or (guess_col < 0 or guess_col > 4):
              print "Your coordonates aren\'t on the board"
          
            
          else:
            if (board[guess_row][guess_col] == "X" or board[guess_row][guess_col] == "H"):
              print "You have typed this coordonates before."
            elif (guess_row < 0 or guess_row > 4) or (guess_col < 0 or guess_col > 4):
              print "Your coordonates aren\'t on the board"
            elif guess_row == ship_row and guess_col == ship_col:
              print "You hit ship 1"
              board[guess_row][guess_col] = "H"
            
            elif guess_row == ship_row2 and guess_col == ship_col2:
              print  "You hit ship 2"
              board[guess_row][guess_col] = "H"  
            
              
            else:
              print "Try again"
              board[guess_row][guess_col] = "X"
          print_board(board)
          if board[ship_row][ship_col]=="H" and board[ship_row2][ship_col2]=="H":
            print "You won the game"
            break
          elif turn == 4:
                print "You lost"
              
if choice in  ["yes","Yes","y"]:
   game(choice)
else:
  print "Exiting game" 



