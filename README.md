python3 --version
mkdir password_strength_analyzer
cd password_strength_analyzer
nano analyzer.py
import re
import math
import getpass

def calculate_entropy(password):
    charset_size = 0
    if re.search(r"[a-z]", password):
        charset_size += 26
    if re.search(r"[A-Z]", password):
        charset_size += 26
    if re.search(r"[0-9]", password):
        charset_size += 10
    if re.search(r"[^a-zA-Z0-9]", password):
        charset_size += 32

    if charset_size == 0:
        return 0

    entropy = len(password) * math.log2(charset_size)
    return round(entropy, 2)

def analyze_password(password):
    score = 0
    feedback = []

    # Length check
    if len(password) >= 12:
        score += 3
    elif len(password) >= 8:
        score += 2
    else:
        feedback.append("Password is too short (use at least 12 characters).")

    # Character variety
    if re.search(r"[a-z]", password):
        score += 1
    else:
        feedback.append("Add lowercase letters.")

    if re.search(r"[A-Z]", password):
        score += 1
    else:
        feedback.append("Add uppercase letters.")

    if re.search(r"[0-9]", password):
        score += 1
    else:
        feedback.append("Add numbers.")

    if re.search(r"[^a-zA-Z0-9]", password):
        score += 1
    else:
        feedback.append("Add special characters (!@#$%).")

    # Common patterns
    common_patterns = ["123", "password", "qwerty", "abc"]
    for pattern in common_patterns:
        if pattern.lower() in password.lower():
            score -= 2
            feedback.append("Avoid common patterns like '123' or 'password'.")
            break

    entropy = calculate_entropy(password)

    # Strength result
    if score >= 7 and entropy >= 60:
        strength = "STRONG"
    elif score >= 5:
        strength = "MEDIUM"
    else:
        strength = "WEAK"

    return strength, entropy, feedback

def main():
    print("\n🔐 Password Strength Analyzer (Terminal Version)")
    print("-" * 45)

    password = getpass.getpass("Enter password (input hidden): ")

    strength, entropy, feedback = analyze_password(password)

    print("\nResults:")
    print(f"Strength : {strength}")
    print(f"Entropy  : {entropy} bits")

    if feedback:
        print("\nSuggestions:")
        for f in feedback:
            print(f"- {f}")
    else:
        print("\nGreat! Your password looks strong.")

if __name__ == "__main__":
    main()
CTRL + X
Y
ENTER
python3 analyzer.py

