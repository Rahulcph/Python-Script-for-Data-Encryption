File Encryption and Decryption Tool 🔒
This Python script provides a simple command-line interface for encrypting and decrypting files using a password. It uses PBKDF2 for key derivation and Fernet for encryption, ensuring your files are secured.

📖 Features
Secure File Encryption
Encrypts files with a password and a randomly generated salt.

Password-Based Decryption
Decrypts files using the same password used during encryption.

Automatic Salt Handling
The salt is securely stored within the encrypted file for seamless decryption.

🛠️ Prerequisites
Python 3.6 or later
cryptography library installed
To install the required library, run:

bash
Kopier kode
pip install cryptography
🚀 Usage
1. Run the Script
Run the script in your terminal or command prompt:

bash
Kopier kode
python encrypt_decrypt.py
2. Choose an Option
The script will prompt you to choose:

(E) to encrypt a file
(D) to decrypt a file
3. Provide File Path and Password
Enter the path to the file you want to encrypt or decrypt.
Input a password. (The password will not be displayed as you type.)
🔐 How It Works
Encryption
Key Derivation
A 32-byte key is derived using the PBKDF2 algorithm with:

SHA-256 hashing
Randomly generated 16-byte salt
100,000 iterations
File Encryption
The file is encrypted using the Fernet encryption scheme and saved with a .enc extension. The salt is prepended to the encrypted data.

Decryption
Salt Retrieval
The first 16 bytes of the encrypted file are read as the salt.

Key Recreation
The password and salt recreate the original key.

File Decryption
The encrypted file is decrypted and saved without the .enc extension.

⚠️ Important Notes
File Removal:
The original file is automatically deleted after encryption or decryption. Ensure you have backups if needed.

Password:
The password must be remembered, as it cannot be recovered. Decryption will fail without the correct password.

📂 Example
Encrypt a File
File: example.txt
Password: mysecurepassword
Result: example.txt.enc is created, and example.txt is deleted.
Decrypt a File
Encrypted File: example.txt.enc
Password: mysecurepassword
Result: example.txt is recreated, and example.txt.enc is deleted.
🛡️ Security
Random Salt ensures unique encryption for the same file and password.
Fernet Encryption guarantees authenticated encryption, ensuring data integrity.
🧑‍💻 Contributing
Feel free to submit issues or create pull requests to enhance this tool. Contributions are welcome!

📜 License
This project is licensed under the MIT License. See the LICENSE file for details.

With this README.md, your project will have a professional and clear presentation on GitHub.
