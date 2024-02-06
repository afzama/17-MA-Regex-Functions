# Credit Card Validation; Masking Sensitive Information

Credit Card Number Validation with sensitive information masking is a crucial aspect of secure and reliable payment processing, contributing to data integrity, user trust, and compliance with industry standards. It's an essential component in creating a secure and trustworthy online transaction environment. This tutorial provides details on expressions designed for effective credit card validation.

## Summary

Credit card number validation using regex involves crafting a pattern that checks the credit card number for adherence to a particular structure. While regex alone cannot perform extensive checks like validating the checksum (Luhn algorithm) for credit card numbers, it can help ensure that the entered number follows a specific format. Below is a breakdown of common regex functions used for credit card validation:

`^(?:4[0-9]{12}(?:[0-9]{3})?| 5[1-5][0-9]{14}|3[47][0-9]{13} 6(?:011|5[0-9][0-9])[0-9]{12} (?:2131|1800|35\d{3})\d{11})$`

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [AdditionalNotes](#additional-notes)
- [Author](#author)

## Regex Components

### Anchors
- `^`: Asserts the start of the string.
- `$`: Asserts the end of the string.

### Quantifiers
- `{12}`: Specifies exactly 12 occurrences of the preceding character or group.
- `?`: Makes the preceding character or group optional (zero or one occurrence).
- `{14}`: Specifies exactly 14 occurrences of the preceding character or group.
- `{13}`: Specifies exactly 13 occurrences of the preceding character or group.
- `{11}`: Specifies exactly 11 occurrences of the preceding character or group.

### OR Operator
- `|`: Acts as the OR operator, allowing multiple alternatives.

### Character Classes
- `[0-9]`: Matches any digit.
- `[1-5]`: Matches any digit from 1 to 5.

### Flags
- There are no flags specified in this regex.

### Grouping and Capturing
- `(?: ... )`: Non-capturing group. Groups multiple patterns but doesn't store the match.
- `(?:4[0-9]{12}(?:[0-9]{3})? ...)`: Non-capturing group for the Visa card pattern.
- `(?:011|5[0-9][0-9])`: Non-capturing group for part of the Discover card pattern.
- `(?:2131|1800|35\d{3})`: Non-capturing group for part of the JCB card pattern.

### Bracket Expressions
- `[0-9]`: Matches any digit.
- `[0-9]{12}`: Matches exactly 12 digits.
- `[0-9]{14}`: Matches exactly 14 digits.
- `[0-9]{13}`: Matches exactly 13 digits.
- `[0-9]{11}`: Matches exactly 11 digits.
- `[a-z]`: Matches any lowercase letter.

### Greedy and Lazy Match
The quantifiers ({12}, {14}, {13}, {11}) are greedy, meaning they match as much as possible. To make them lazy, you would add a ? after each quantifier, but in this case, greediness doesn't affect the functionality.

## Additional Notes
The aforementioned Luhn algorithm (used in mod-10 algorithm), is a simple checksum formula used to validate a variety of identification numbers, including credit card numbers. It helps ensure the accuracy of the entered number and detects accidental errors in the data. The LUHN formula was created in the late 1960s by a group of mathematicians to detect all single-digit errors, as well as almost all transpositions of adjacent digits. You can read more about its use in credit card number validation [here] (https://www.dcode.fr/luhn-algorithm).
Note, Luhn algorithm is not foolproof against intentional fraud, as it primarily detects accidental errors rather than intentional manipulation of digits. 


## Author
This tutorial was prepared by Maria Afzal, a University of Toronto, full stack web development student excited to contribute her learnings with the developer community. For more details visit my GitHub profile [here] (https://github.com/afzama).
