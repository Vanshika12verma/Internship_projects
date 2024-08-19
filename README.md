# Internship_project

1.CALCULATOR
def add(x,y):
    return x+y
def subtract(x,y):
    return x-y
def multiply(x,y):
    return x*y
def divide(x,y):
    if y==0:
        return "Error! Division by zero."
    else:
        return x/y
def calculator():
    print("Select operator")
    print("1,Add")
    print("2,Subtract")
    print("3,Multiply")
    print("4,Divide")
    
    choice = input("Enter choice(1/2/3/4):")
    
    if choice in ['1','2','3','4']:
        num1 = float(input("Enter first number: "))
        num2 = float(input("Enter second number: "))
        
        if choice=='1':
            print(f"The result is {add(num1,num2)}")
        elif choice=='2':
            print(f"The result is {subtract(num1,num2)}")
        elif choice=='3':
            print(f"The result is {multiply(num1,num2)}")
        elif choice=='4':
            print(f"The result is {divide(num1,num2)}")
        else:
            print("Invalid input")
calculator()
  
  
    
print("Select operator")
print("1.Add")
print("2.Subtract")
print("3.Multiply")
print("4.Divide")
a = float(input("Enter choice(1/2/3/4): "))
b = float(input("Enter first number: "))
c = float(input("Enter second number: "))
if a==1:
    print("The result is ",b+c)
elif a=='2':
    print("The result is ",b-c)
elif a=='3':
    print("The result is: ",b*a)
else:
    print("The result is: ",b/a)

    

#GUESS THE NUMBER

def guess_number():
    number_to_guess = int(input("Player 1, enter a number between 1 and 100: "))
    print("\n"*50)
    
    attempts = 0
    while True:
        guess = int(input("Player 2,guess the number: "))
        attempts+=1
        
        if guess < number_to_guess:
            print("Too low!")
        elif guess > number_to_guess:
            print("Too high")
        else:
            print(f"Correct!You guessed it in {attempts}attempts.")
            break
guess_number()


#TIC-TAC-TOE

def print_board(board):
    for row in board:
        print("|".join(row))
        print("-"*5)

def check_winner(board,player):
    for i in range(3):
        if all([spot == player for spot in board[i]]):
            return True
        if all([board[i][i] == player for i in range(3)]):
            return True
        if all([board[i][2-i] == player for i in range(3)]):
            return True
        return False
def is_board_full(board):
    return all([spot != ""for row in board for spot in row])
def tic_tac_toe():
    board = [["" for _ in range(3)]for _ in range(3)]
    current_player = "X"
    
    while True:
        print_board(board)
        print(f"Player{current_player},it's your turn.")
    
        try:
            row,col = map(int,input("Enter row and column numbers(1-3)seperated by a space:").split())
            if board[row-1][col-1]!="":
                print("That spot is already taken.Try again.")
                continue
        except(ValueError,IndexError):
            print("Invalid input.Please enter row and column numbers between 1 and 3.")
            continue
        board[row-1][col-1] = current_player
        
        if check_winner(board,current_player):
            print_board(board)
            print(f"Player{current_player}wins!")
            break
        elif is_board_full(board):
            print_board(board)
            print("It is a tie!")
            break
        current_player = "0"if current_player=="X" else"X"
tic_tac_toe()


#ROCK,PAPER AND SCISSOR

a = "Rock,Paper and Scissor Game: "
b = input("It's your turn: ")
c = "Rock" or "Paper" or "Scissor"
if b=="Rock" or b=="Paper" or b=="Scissor":
    if b==c:
        print("It's a draw")
elif b=="Rock" and c=="Paper":
    print("You lose")
elif b=="Rock" or c=="Scissor":
    print("You win")
elif b=="Paper" or c=="Paper":
    print("It's a draw")
elif b=="Paper" or b=="Rock":
    print("You lose")
elif b=="Paper" or b=="Scissor":
    print("You win")
elif b=="Scissor" or b=="Rock":
    print("You win")
elif b=="Scissor" or b=="Paper":
    print("You lose")
else:
    print("It's a draw")


#ROCK,PAPER AND SCISSOR

print('Winning rules of the game ROCK PAPER SCISSORS are :\n'
      + "Rock vs Paper -> Paper wins \n"
      + "Rock vs Scissors -> Rock wins \n"
      + "Paper vs Scissors -> Scissor wins \n")
print("Enter choice ")
print("1. Rock")
print("2. Paper")
print("3. Scissors")
a = int(input("Enter your choice: "))
x = int(input("Enter second player choice: "))
b = "1"
c = "2"
d = "3"
while a>=1 and a<=3:
    if a==b or a==c:
        print("It's a draw")
    elif a==1 and x==1:
        print("It's a draw")
    elif a==1 and x==2:
        print("You lose")
    elif a==1 and x==3:
        print("You win")
    elif a==2 and x==1:
        print("You win")
    elif a==2 and x==2:
        print("It's a draw")
    elif a==2 and a==3:
        print("You lose")
    elif a==3 and a==1:
        print("You lose")
    elif a==3 and x==2:
        print("You win")
    else:
        print("It's a draw")
