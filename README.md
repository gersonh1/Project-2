rng will represent what holds the random words for the hangman
import random
rng = ["WFIDSPQZ", "XHO' 'TTDBFRT", "QQJYF", "ENQD", "DNPK", "CNTR", "EHWHOD", "TSVMOHOF", "XNOCFQGTM"]
randomW = random.choice(rng)
random.choice will randomly select a word among the 9 available
print("Current word")
guesses = ''
turns = 10
The code will run until the user has entered 10 letters
while turns > 0:
   fail = 0
   for char in randomW:
       if char in guesses:
           print(char)
       else:
           print("_")
           fail += 1          
   if fail == 0:
   this will print when the user guesses the right word.
       print("YAY! You guessed the word ", randomW, "!!")
       print("This was the encrypted message!")
       print("The decoded message says: ", randomW)
       break 
  This will be displayed and ask user what their input would be.      
   guess = input("Guess a letter:")  
   guesses += guess
   if guess not in randomW:
       turns -= 1
       print("Your letter,", guess, " is not in the word.")
       print("You have ", + turns, ' lives left and you have used these letters: ', guesses)
       if turns == 0:
           print("\nYou weren't able to uncover the word")
           print("The word is:", randomW)
