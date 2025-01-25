import random
import string

# Pre-defined lists of adjectives and nouns
adjectives = ["Happy", "Cool", "Fast", "Bright", "Smart", "Brave"]
nouns = ["Tiger", "Dragon", "Eagle", "Phoenix", "Wolf", "Bear"]

def generate_username(length=8, include_numbers=True, include_special_chars=True):
    """Generate a username by combining random adjectives and nouns."""
    adj = random.choice(adjectives)
    noun = random.choice(nouns)
    username = adj + noun

    # Add numbers if enabled
    if include_numbers:
        username += str(random.randint(0, 999))

    # Add special characters if enabled
    if include_special_chars:
        username += random.choice("!@#$%^&*")

    # Truncate or pad the username to match the desired length
    if len(username) < length:
        username += ''.join(random.choices(string.ascii_letters + string.digits, k=length - len(username)))
    else:
        username = username[:length]

    return username

def save_usernames_to_file(usernames, filename="usernames.txt"):
    """Save a list of usernames to a text file."""
    with open(filename, "w") as file:
        for username in usernames:
            file.write(username + "\n")
    print(f"Usernames saved to {filename}")

def main():
    print("Welcome to the Random Username Generator!")
    
    # Get user preferences
    num_usernames = int(input("How many usernames would you like to generate? "))
    length = int(input("Enter the desired length of the usernames: "))
    include_numbers = input("Include numbers? (yes/no): ").strip().lower() == "yes"
    include_special_chars = input("Include special characters? (yes/no): ").strip().lower() == "yes"

    # Generate usernames
    usernames = [
        generate_username(length, include_numbers, include_special_chars)
        for _ in range(num_usernames)
    ]

    # Display the usernames
    print("\nGenerated Usernames:")
    for username in usernames:
        print(username)

    # Save to file
    save_option = input("\nWould you like to save these usernames to a file? (yes/no): ").strip().lower()
    if save_option == "yes":
        save_usernames_to_file(usernames)

if __name__ == "__main__":
    main()
