#!/bin/bash

# Function to get the number of files in the current directory
get_file_count() {
    ls -1 | wc -l
}

# Get the actual number of files
file_count=$(get_file_count)

echo "Welcome to the Guessing Game!"
echo "How many files are in the current directory? Take a guess!"

# Loop until the correct guess
while true; do
    read -p "Enter your guess: " user_guess
    if [[ $user_guess -eq $file_count ]]; then
        echo "Congratulations! You guessed the correct number of files!"
        break
    elif [[ $user_guess -lt $file_count ]]; then
        echo "Too low! Try again."
    else
        echo "Too high! Try again."
    fi
done
