# CodeAlpha - Secure Coding Review

## Project Overview

This project reviews a simple Python login application to identify common security vulnerabilities and recommend secure coding practices.

---

# Code Reviewed

```python
username = input("Enter Username: ")
password = input("Enter Password: ")

if username == "admin" and password == "admin123":
    print("Login Successful")
else:
    print("Invalid Username or Password")
```

---

# Security Vulnerabilities Found

## 1. Hardcoded Credentials

### Issue
The username and password are written directly inside the source code.

### Risk
Anyone who can read the code can see the credentials.

### Recommendation
Store credentials securely in a database or use password hashing.

---

## 2. Plain Text Password

### Issue
The password is stored in plain text.

### Risk
If the code is leaked, the password is immediately exposed.

### Recommendation
Use hashed passwords with libraries such as bcrypt.

---

## 3. No Password Masking

### Issue
The password is visible while typing.

### Risk
Someone nearby can easily see the password.

### Recommendation
Use Python's getpass module.

---

## 4. No Login Attempt Limit

### Issue
Users can try unlimited passwords.

### Risk
This allows brute-force attacks.

### Recommendation
Limit failed login attempts and temporarily lock the account.

---

## 5. No Logging

### Issue
The application does not record login attempts.

### Risk
Suspicious activities cannot be monitored.

### Recommendation
Maintain secure log files.

---

# Overall Risk Level

Medium

---

# Conclusion

The application works correctly but is not secure for real-world use. Implementing password hashing, secure credential storage, login attempt limits, logging, and password masking would significantly improve security.