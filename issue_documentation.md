# Lab 5: Static Code Analysis

## Issues Found and Fixes

| Issue | Type | Location | Description | Fix |
|---|---|---|---|---|
| Unsafe pickle deserialization | Security | Original line 67 | pickle.load() can execute malicious code when loading untrusted files. | Replaced pickle with JSON serialization and deserialization. |
| Hardcoded password | Security | Original line 8 | A password was stored directly in source code. | Read the password from the SYNC_PASSWORD environment variable. |
| Broad exception handling | Code quality | Original updateCity() | except Exception can hide unrelated errors. | Check whether the contact exists before updating it. |
| Formatting violations | Style | Original lines 23, 47, 84, 85 | Missing whitespace, excessive blank lines, and a long line. | Reformatted code and wrapped long lines. |
| Inconsistent naming | Maintainability | Multiple functions | Function names used camelCase instead of snake_case. | Renamed functions using Python naming conventions. |

## Reflection

### 1. What is static code analysis?
It examines source code without executing it to identify potential bugs, security vulnerabilities, and style violations.

### 2. What are the roles of the three tools?
Pylint checks code quality and programming practices. Bandit identifies potentially insecure Python patterns. Flake8 checks formatting and PEP 8 compliance.

### 3. Why is pickle.load() dangerous?
Loading an untrusted pickle file may execute arbitrary code. JSON is safer for ordinary contact data because it does not deserialize arbitrary Python objects.

### 4. How did static analysis improve the program?
It helped identify security risks, broad exception handling, naming inconsistencies, and formatting problems.

### 5. Why should static analysis be used regularly?
It helps identify issues early, improves maintainability, promotes consistent coding practices, and reduces security risks.

## Verification
Before-and-after reports are included for Pylint, Bandit, and Flake8. The final observed Pylint score was 10.00/10. Bandit and Flake8 reports should be retained to document the final checks.
