import random

def board():
    for i in range(3): 
        print("\n+---+---+---+")
        print("|", end="")
        for j in range(3):
            print(f" {m[i][j]} |", end="")
    print("\n+---+---+---+")

def array(n, turn):
    if n == 0:
        m[0][0] = turn
    elif n == 1:
        m[0][1] = turn
    elif n == 2:
        m[0][2] = turn 
    elif n == 3:
        m[1][0] = turn
    elif n == 4:
        m[1][1] = turn
    elif n == 5:
        m[1][2] = turn        
    elif n == 6:
        m[2][0] = turn
    elif n == 7:
        m[2][1] = turn 
    elif n == 8:
        m[2][2] = turn 

def check_win(m, turn):
    # Check rows, columns, and diagonals for a win
    for i in range(3):
        if all([m[i][j] == turn for j in range(3)]) or all([m[j][i] == turn for j in range(3)]):
            return True
    if m[0][0] == m[1][1] == m[2][2] == turn or m[0][2] == m[1][1] == m[2][0] == turn:
        return True
    return False

def game():
    print("Welcome")
    print("Choose your mode")
    print("1. Easy\n2. Average\n3. Hard")
    a = int(input(":"))

    # Placeholder functions for different difficulties
    def easier():
        return "Easy mode selected"
    
    def average():
        return "Average mode selected"
    
    def harder():
        return "Hard mode selected"

    if a == 1:
        print(easier())
    elif a == 2:
        print(average())
    else:
        print(harder())

    global m
    m = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
    board()
    turn = "X"

    for _ in range(9):
        n = int(input(f"Player {turn}, enter your move (0-8): "))
        array(n, turn)
        board()
        if check_win(m, turn):
            print(f"Player {turn} wins!")
            return
        turn = "O" if turn == "X" else "X"
    
    print("It's a tie!")

game()
