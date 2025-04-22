# Password-Manager
A command-line password manager written in C that allows users to generate, encrypt, save, and retrieve passwords securely. Passwords are encrypted using a custom XOR-based cipher and stored in a text file.

## Features
Generate strong, random passwords.

Encrypt and decrypt passwords using a unique key.

Save encrypted passwords with service names to passwords.txt.

Retrieve and decrypt passwords by specifying the service name.

Uses low-level file I/O (e.g., open, read, write) for manual file operations.

## File Structure
password_manager.c – Main source code file.

passwords.txt – Stores service names, encrypted passwords (in hex), and encryption keys.

## How It Works
Generate Password: User can choose to generate a random password or enter one manually.

Generate Key: A random encryption key is generated for each password.

Encrypt Password: XOR cipher is applied using the key.

Save Password: The encrypted password (in hex) and key are stored in passwords.txt along with the associated service name.

Retrieve Password: By providing the service name, the program searches the file, decrypts the password using the saved key, and displays it.

## Example Output
Do you want to generate a random password or set a custom password? (R/C): r
Generated Random Password: STm)K!k#7DQAo1#
Generated Random Key: TKg_V)x@4XZPu3@
Encrypted Password (hex): 071f0a761d081363031c0b111a0263
Password saved successfully for service: Facebook
DEBUG: Searching for service 'Facebook'...
DEBUG: Checking service: 'Facebook'
Service: Facebook
Decrypted Password: STm)K!k#7DQAo1#

## Compilation
gcc -o password_manager password_manager.c
./password_manager

## Notes
* The encryption is based on XOR logic and should not be considered cryptographically secure for production use.

* Always keep passwords.txt in a secure location and avoid sharing your keys.


