import random

def generatepasswords(passwordlength,z):
    
    words = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789"
    
    if z=="yes" or z=="Yes" or z=="YES":
        
        words+="!@#$&?"
        
    mainpassword = []
    
    for i in passwordlength:
        
        password = ""
        
        for j in range(i):
            
            letterindex = random.randrange(len(words))
            
            password += words[letterindex]
            
        mainpassword.append(password)
        
    return mainpassword


def maincode():
    
    nopasswords = int(input("PLEASE ENTER THE NUMBER OF PASSWORDS YOU WANT: "))
    
    print("...../GENERATING",nopasswords,"PASSWORDS PLEASE FILL UP THE FOLLOWING DETAILS/.....")
    
    q=input("DO YOU WANT SYMBOLS (!@#$&?) IN YOUR PASSWORD? IF (yes) THEN ENTER YES OTHERWISE ENTER ANY CHARACTER: ")
    
    passwordlen = []
    
    print("(PLEASE NOTE) THE LENGTH OF THE PASSWORD SHOULD BE GREATER THAN 4.")
    
    for i in range(nopasswords):
        
        length=int(input("ENTER THE LENGTH OF YOUR PASSWORD: "))
        
        if length <= 4:
            
            while length <= 4:
                
                length=int(input("ERROR!! PLEASE ENTER LENGTH GREATER THAN 4: "))
                
        passwordlen.append(length)
        
    password = generatepasswords(passwordlen,q)
    
    for i in range(len(password)):
      
        
        
        print("PASSWORD",i+1,"=",password[i])
        
        
maincode()
#OK