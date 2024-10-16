import random

def get_user_choice():
    user_input = input("Enter your choice (1.stone, 2.paper, 3.scissor): ").lower()
    while user_input not in ['stone', 'paper', 'scissor']:
        user_input = input("Invalid choice. Please enter stone, paper, or scissor: ").lower()
    return user_input

def get_computer_choice():
    return random.choice(['stone', 'paper', 'scissor'])

def determine_winner(user_choice, computer_choice):
    if user_choice == computer_choice:
        return "It's a tie!"
    elif (user_choice == 'stone' and computer_choice == 'scissor') or \
         (user_choice == 'paper' and computer_choice == 'stone') or \
         (user_choice == 'scissor' and computer_choice == 'paper'):
        return "You win!"
    else:
        return "Computer wins!"

def play_game():
    user_choice = get_user_choice()
    computer_choice = get_computer_choice()
    print(f"You chose: {user_choice}")
    print(f"Computer chose: {computer_choice}")
    result = determine_winner(user_choice, computer_choice)
    print(result)

if __name__ == "__main__":
    play_game()
