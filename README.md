import random

def guess_number():
    number = random.randint(1, 100)
    attempts = 0

    print("Welcome to the Number Guessing Game!")
    print("I'm thinking of a number between 1 and 100. Can you guess it?")

    while True:
        guess = input("Enter your guess (or 'q' to quit): ")
        
        if guess.lower() == 'q':
            print("Quitting game. The number was:", number)
            break
        
        try:
            guess = int(guess)
        except ValueError:
            print("Please enter a valid number.")
            continue
        
        attempts += 1

        if guess < number:
            print("Too low! Try again.")
        elif guess > number:
            print("Too high! Try again.")
        else:
            print(f"Congratulations! You guessed the number in {attempts} attempts.")
            break

guess_number()
