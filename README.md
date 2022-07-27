# Regex Helpher

In this helper a few key elements of a regular expression will be covered. The main example that will be covered is an email string and how it is made into different sections using regex. Regular expression concepts can be very confusing. This helper will put some of that information into terms that are hopefully easier on the brain.

## Summary

Regex is short for regular expression and the regex that we will go over in this helper refers to email. Each of the elements in the regex will be covered also their representation and function in the expression. 

This is the regex code snippet for email: - `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

It is a little intimidating at first glance don't panic

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)

## Regex Components

The start to any regex it must have `/` wrapper. This tells what is in the string also makes the foundation to make a regex. You must have `/` at the beginning and end of every regex.

### Anchors

The anchor/anchors used in this email code snippet above is `^` behind the initial `/` and the $ before the last `/`. Anchors let the regex because they indicate what is able to be in the string also what is trying to be found or searched for. The anchor being used will either represent a string beginning with that character (`^`) and/or a string that ends with that character (`$`). 

### Quantifiers

Quantifiers set the amount of times a string matches in your expression. In the email code snippet the quantifiers being userd are - `+` and `{}`

The `+` quantifier means tells the regex the string elements passed before have to match at least one time. Meaning the one "acceptance" criteria we selected in the `[]` have to match.

Also the `{}` quantifiers that are 2 and 6 in this case the first number means the minimum and the 6 means the maximum amount of matches to meet the "acceptance" criteria. If you type `{2}` that sets the value to exactly that number to match the "acceptance" criteria. If you type `{3,}` it sets the minimum value to the number indicated to meet the "acceptance" criteria.

### Grouping Constructs


Grouping or capturing is a way to divide  sections or aspects of your expression, if you want to check for different values or characters through different sections of the string.

In our example, we use parentheses (`()`) to divide our sections.

The first set of parentheses that we see are before the `@` symbol in our email string so the entire section of `([a-z0-9_\.-]+)` is looking for and a capturing different values than the half that follows the `@` symbol being `([\da-z\.-]+)\.([a-z\.]{2,6})` which is looking for some type of domain like "@gmail.com".

Grouping and capturing is helpful because it cleans up the expression and allows you to search for different aspects depending upon what we are trying to create. A password may need different sections also a username, or in our case email address.


### Bracket Expressions
The bracket expressions used in the above regex are:

- `[a-z0-9_\.-]`
- `[\da-z\.-]`
- `[a-z\.]`

Bracket expressions are the backbone of regex, they signify the types of characters or values that we want to include within our string.

In our expression, the `[a-z]` portion of the expression means the string contains only lowercase characters between a-z in the alphabet. The bracket expressions are case-sensitive this means if you want to include uppercase characters, you will have to include `[A-Z]` somewhere in the expression to include the uppercase values.

The next section of the bracket expression is `[0-9]` which indicated the string can contain any numeric value between 0-9.

The last piece of the bracket expressions is the special characters that you want to include, which are  prevalent, especially in the case of emails. In our expression above, you have `[.]`, `[_]`, and `[-]`. These values mean that you can have an underscore(`[_]`), a period(`[.]`), or hyphen(`[-]`) in the email string.

### Character Classes

Character classes define specific sets of characters that are included in the string and would qualify for our "match pattern" parameters that we set up with the quatifiers.

In the expression above, the character classes that are being used are:

- `.` in the `\.([a-z\.]{2,6})$/` section and `\d` in the `[\da-z\.-]` section.

The first character class that you see is the `.`, this is used in the regex in the bracket expressions following a `\`. The `\` is considered a "character escape" when it's nested in a bracket expression it. The `.` character class means that whatever character or values it precedes, matches any character except the "newline" character which is `\n`(responsible for creating a new line. The period in the example represents some sort of break that you are expecting after certain requirements are met. you are looking some sort of ".com" or ".org" after the section `@([\da-z\.-]+)` is met.

The main character class that is in the regex is `\d` and this means that it matches a Arabic numerical digit. So, Numeric values between `[0-9]`. In our expression `[\da-z\.-]`, the `\d` represents any numeric value and "a-z".


## Author

Jaryodd Carter

University of Denver Student, currently in the Full-Stack Coding Bootcamp

Feel free to use the links below to contact me 

- Email: jaryodd@gmail.com
- GitHub: https://github.com/Jaryodd
