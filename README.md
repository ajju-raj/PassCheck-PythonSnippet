# Password Strength Checker

This project is a **basic password strength checker** that evaluates password security using multiple methods. It's designed as the **0th project** in your cybersecurity journey and incorporates one of the most advanced password strength-checking libraries, `zxcvbn`, as well as custom password validation checks.

## Features

- **Common Password Check**: Verifies whether the password appears in a list of 10 million commonly used passwords.
- **Password Length Evaluation**: Checks for a minimum length of 8 characters, with better scores for longer passwords.
- **Character Type Check**: Ensures the password contains a mix of lowercase letters, uppercase letters, digits, and special characters (`$#@`).
- **Advanced Password Strength Analysis**: Uses the `zxcvbn` library to provide detailed feedback on password strength, including crack times and suggestions.
- **Detailed Feedback**: Provides warnings and recommendations to improve password security.

## Requirements

- **Python 3.x**
- The following Python libraries:
  - `re`: For regular expression-based checks.
  - `getpass`: To securely take user input.
  - `zxcvbn`: To analyze password strength.
  - `json`: For formatting results.
  - `decimal`: For handling numeric types in the output.
  - `datetime`: For managing time-based results.

## Installation

1. Install Python 3.x from the [official Python website](https://www.python.org/downloads/).
2. Install the required `zxcvbn` library:
   ```bash
   pip install zxcvbn
   ```
3. Clone or download this repository.
4. Ensure you have the **Common Pass 10M.txt** file in the same directory or update the path in the code accordingly. The file contains 10 million common passwords to compare against.

## Usage

1. Run the script using the following command in your terminal:
   ```bash
   python strength0.py
   ```
2. Enter your password when prompted:
   ```
   Enter your password:
   ```

3. The script will perform multiple checks:
   - **Common Password Check**: It will exit and prompt you to choose a different password if your password is found in the list.
   - **Custom Checks**: It will evaluate the password based on length and character types (lowercase, uppercase, numbers, special characters).
   - **zxcvbn Analysis**: It provides detailed feedback, warnings, suggestions, and estimates of how long it would take to crack your password using various attack methods.

4. Example output:
   ```
   Enter your password:
   {feedback: "No warnings", suggestions: "Use a few words, avoid common phrases.", time_to_crack: "10 years"}
   Password strength score: 3 (Out of 4)

   Password is medium 5 / 7
   ```

## File Structure

```
├── PassStrengthCheck-0.py                # Main password strength checker script
├── Common Pass 10M.txt          # List of 10 million common passwords (used in common password check)
└── README.md                    # Documentation (this file)
```

## Explanation of the Code

### Custom Password Check
- **Common Password Check**: The script reads the common passwords file and compares your input against the list. If it matches, it prompts you to choose a different password.
- **Length & Character Check**: The script checks if your password meets minimum length requirements (8 characters) and evaluates its composition (lowercase, uppercase, digits, special characters).

### zxcvbn Library
- The `zxcvbn` library performs a more in-depth analysis, considering patterns, repeated sequences, and other password features.
- It provides feedback, suggestions, and an estimated time to crack the password using different attack methods (e.g., throttled online attack).

### Output
- A combination of feedback from the custom checks and the `zxcvbn` analysis is displayed to the user, along with a final strength score and advice on improving the password.

## Contributing

Feel free to contribute to this project by submitting a pull request or suggesting new features or improvements.

## License

This project is licensed under the MIT License.
