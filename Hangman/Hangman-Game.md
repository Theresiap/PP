## Hangman Code
```markdown
import random

WORDLIST_FILENAME = "words.txt"

def loadWords():
    """
    Returns a list of valid words. Words are strings of lowercase letters.
    
    Depending on the size of the word list, this function may
    take a while to finish.
    """
    print("Loading word list from file...")
    # inFile: file
    inFile = open(WORDLIST_FILENAME, 'r')
    # line: string
    line = inFile.readline()
    # wordlist: list of strings
    wordlist = line.split()
    print("  ", len(wordlist), "words loaded.")
    return wordlist

def chooseWord(wordlist):
    """
    wordlist (list): list of words (strings)

    Returns a word from wordlist at random
    """
    return random.choice(wordlist)

# Load the list of words into the variable wordlist so that it can be accessed from anywhere in the program
wordlist = loadWords()

def isWordGuessed(secretWord, lettersGuessed):
    '''
    secretWord: string, the word the user is guessing
    lettersGuessed: list, what letters have been guessed so far
    returns: boolean, True if all the letters of secretWord are in lettersGuessed;
      False otherwise
    '''
    # FILL IN YOUR CODE HERE...



def getGuessedWord(secretWord, lettersGuessed):
    '''
    secretWord: string, the word the user is guessing
    lettersGuessed: list, what letters have been guessed so far
    returns: string, comprised of letters and underscores that represents
      what letters in secretWord have been guessed so far.
    '''
    # FILL IN YOUR CODE HERE...



def getAvailableLetters(lettersGuessed):
    '''
    lettersGuessed: list, what letters have been guessed so far
    returns: string, comprised of letters that represents what letters have not
      yet been guessed.
    '''
    # FILL IN YOUR CODE HERE...
    

def hangman(secretWord):
    '''
    secretWord: string, the secret word to guess.

    Starts up an interactive game of Hangman.

    * At the start of the game, let the user know how many 
      letters the secretWord contains.

    * Ask the user to supply one guess (i.e. letter) per round.

    * The user should receive feedback immediately after each guess 
      about whether their guess appears in the computers word.

    * After each round, you should also display to the user the 
      partially guessed word so far, as well as letters that the 
      user has not yet guessed.

    Follows the other limitations detailed in the problem write-up.
    '''

# secretWord = chooseWord(wordlist).lower()
# hangman(secretWord)

def isWordGuessed(secretWord, lettersGuessed):
    result = True
    for x in secretWord:
        if not (x in lettersGuessed):
            result = False
    return result

def getGuessedWord(secretWord, lettersGuessed):
    result = ""
    for x in secretWord:
        if (x in lettersGuessed):
            result = result + x
        else:
            result = result + '_'
    return result
    
print(getGuessedWord(secretWord, lettersGuessed))

def getAvailableLetters(lettersGuessed):
    alphabet = 'abcdefghijklmnopqrstuvwxyz'
    for x in lettersGuessed:
        alphabet = alphabet.replace(x, '')
    return alphabet
    
print(getAvailableLetters(lettersGuessed))

def hangman(secretWord):
    lettersGuessed = ''
    availableLetters = 'abcdefghijklmnopqrstuvwxyz'
    chances = 8
    print('Welcome to the game Hangman!')
    print('I am thinking of a word that is '+str(len(secretWord))+' letters long.')
    while True:
        print('-----------')
        print('You have '+str(chances)+' guesses left')
        print('Available letters: '+availableLetters)
        x = input('Please guess a letter: ')
        if x in lettersGuessed:
            print('Oops! You\'ve already guessed that letter: '+getGuessedWord(secretWord, lettersGuessed))
            continue
            
        lettersGuessed = lettersGuessed + x
        availableLetters = getAvailableLetters(lettersGuessed)
        if x in secretWord:
            print('Good guess: '+getGuessedWord(secretWord, lettersGuessed))
        else:
            chances = chances - 1
            print('Oops! That letter is not in my word: '+getGuessedWord(secretWord, lettersGuessed))

        if isWordGuessed(secretWord, lettersGuessed):
            print('-----------')
            print('Congratulations, you won!')
            break
              
        if chances == 0:
            print('-----------')            
            print('Sorry, you ran out of guesses. The word was '+secretWord+'. ')
            break
hangman('You can put anything here')
```
