# Exploring-Text-Encryption-and-Decryption-in-Python-using-Caesar_Cipher-algorithm
def encrypt_caesar_cipher(text, shift):
    encrypted_text = ""
    for char in text:
        if char.isalpha():
            # Handle uppercase letters
            if char.isupper():
                encrypted_text += chr((ord(char) + shift - 65) % 26 + 65)
            # Handle lowercase letters
            else:
                encrypted_text += chr((ord(char) + shift - 97) % 26 + 97)
        else:
            encrypted_text += char  # Non-alphabetic characters remain unchanged
    return encrypted_text

def decrypt_caesar_cipher(text, shift):
    decrypted_text = ""
    for char in text:
        if char.isalpha():
            # Handle uppercase letters
            if char.isupper():
                decrypted_text += chr((ord(char) - shift - 65) % 26 + 65)
            # Handle lowercase letters
            else:
                decrypted_text += chr((ord(char) - shift - 97) % 26 + 97)
        else:
            decrypted_text += char  # Non-alphabetic characters remain unchanged
    return decrypted_text

def main():
    while True:
        choice = input("Do you want to (E)ncrypt, (D)ecrypt or (Q)uit? ").upper()
        if choice == 'Q':
            print("Goodbye!")
            break
        elif choice not in ['E', 'D']:
            print("Invalid choice, please choose E, D, or Q.")
            continue
        
        text = input("Enter the message: ")
        shift = int(input("Enter the shift value: "))
        
        if choice == 'E':
            encrypted = encrypt_caesar_cipher(text, shift)
            print("Encrypted Message:", encrypted)
        elif choice == 'D':
            decrypted = decrypt_caesar_cipher(text, shift)
            print("Decrypted Message:", decrypted)

if __name__ == "__main__":
    main()


