import random

def get_user_choice():
    while True:
        user_choice = input("Enter your choice (rock, paper, or scissors), or type 'quit' to end the game: ").lower()
        if user_choice in ['rock', 'paper', 'scissors', 'quit']:
            return user_choice
        else:
            print("Invalid choice. Please enter rock, paper, scissors, or quit.")

def get_computer_choice():
    return random.choice(['rock', 'paper', 'scissors'])

def determine_winner(user_choice, computer_choice):
    if user_choice == computer_choice:
        return "It's a tie!"
    elif (user_choice == 'rock' and computer_choice == 'scissors') or \
         (user_choice == 'paper' and computer_choice == 'rock') or \
         (user_choice == 'scissors' and computer_choice == 'paper'):
        return "You win!"
    else:
        return "Computer wins!"

def play_game():
    while True:
        print("\nLet's play Rock, Paper, Scissors!")
        user_choice = get_user_choice()
        if user_choice == 'quit':
            print("Thanks for playing!")
            break
        computer_choice = get_computer_choice()
        print("You chose:", user_choice)
        print("Computer chose:", computer_choice)
        print(determine_winner(user_choice, computer_choice))

play_game()
