import random 
print(" wecolome")
print ("choise your mode ")
print("1 easy , 2 avrage, 3 hard")
a=input(":")
def choise(a):
    if (a==1):
        print(easier())
    elif(a==2):
        print(avrager())
    else:
        print(harder())
m = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
row = 3
col = 3
def bord():
    for i in range(row): 
        print("\n+---+---+---+")
        print("|", end="")
        for j in range(col):
            print(f" {m[i][j]} |", end="")
    print("\n+---+---+---+")
bord()

def array (n,tun):
    tun="x"
    n =-1
    if(n==0):
        m[0,0]==tun
    elif(n==1):
        m[0,1]==tun
    elif(n==2):
        m[0,2]==tun 
    elif(n==3):
        m[1,0]==tun
    elif(n==4):
        m[1,1]==tun
    elif(n==5):
        m[1,2]==tun        
    elif(n==6):
        m[2,0]==tun
    elif(n==7):
        m[2,1]==tun 
    elif(n==8):
        m[2,2]==tun 
    leave=False    
def win(m,tun,leave,i,j):

    while (leave==False):
        if(tun ==m[i]):
            print("u win")
        elif( tun==m[i,j-1]):
            print("u win")
        elif( tun==m[i-1,j]):
            print("u win")
        elif(tun==m[i-1,j+1]):
            print("u win") 
            
