MDP = ""
D = 0
CC = ""

def saisie(MDP : str):
    # this function is used to code a password
    MDP = input("Enter your password: ")
    while len(MDP) > 10 :
        print("Your password is too long, please enter a password with a maximum of 10 characters")
        MDP = input("Enter your password: ")
    return MDP
def saisie2(D : int):
    D = int(input("Enter the D :"))
    while D < 1 and D > 5 :
        print("D must be between 1 and 5")
        D = int(input("Enter the D :"))
    return D
def saisieCC(CC : str , MDP: str):
    CC = input("enter the CC , the CC must be 0 and 1 only and has the same lenght of MDP :")
    while verifaction == False and len(CC) != len(MDP) :
        print("CC must be 0 and 1 only and has the same lenght of MDP")
        CC = input("enter the CC , the CC must be 0 and 1 only and has the same lenght of MDP :")
    return CC
def modification(MDP: str  , D: int  , CC: str):
    # this function is used to modify the password according to the D and CC
    X = MDP
    Y = ""
    MDP2 = ""
    for i in range(len(MDP)):
       
        if CC[i] == "1" :
            
           Y = chr(ord(X[i]) + D)
           MDP2 += Y
        else:
            Y = chr(ord(X[i]) - 0)
            MDP2 += Y
    return str(MDP2)
def affichage(MDP2: str , D: int , CC: str):
    # this function is used to display the password
    print("The password is : ", MDP2)
    print("The D is : ", D)
    print("The CC is : ", CC)
def verifaction(CC: str , MDP: str):
    # this function is used to verify the CC 
    for i in range(len(MDP)):
        test = False
        if CC[i] == "1" or "0":
            test = True
    return test

# this function is used to code a password
MDP = saisie(MDP)
D = saisie2(D)
CC = saisieCC(CC , MDP)
MDP = modification(MDP , D , CC)
affichage (MDP , D , CC)
