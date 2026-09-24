# pinextractor
🔐 Poem PIN Extractor

A simple Python program that extracts secret numeric codes from poems by using the length of specific words on each line.

📌 How It Works

The pin_extractor() function takes a list of poems and generates a secret code for each poem.

For each line:

The line is split into individual words.
The program selects the word at the position corresponding to the line number.
The length of that word is added to the secret code.
If the line doesn't contain enough words, 0 is added instead.
Example

For:

Stars and the moon
shine in the sky
white and
until the end of the night

The program checks:

Line	Line Index	Selected Word	Length
Stars and the moon	0	Stars	5
shine in the sky	1	in	2
white and	2	—	0
until the end of the night	3	the	3

So the resulting secret code is:

5203

💻 Code

def pin_extractor(poems):
    secret_codes = []

    for poem in poems:
        secret_code = ''
        lines = poem.split('\n')

        for line_index, line in enumerate(lines):
            words = line.split()

            if len(words) > line_index:
                secret_code += str(len(words[line_index]))
            else:
                secret_code += '0'

        secret_codes.append(secret_code)

    return secret_codes


poem = """Stars and the moon
shine in the sky
white and
until the end of the night"""

poem2 = 'The grass is green\nhere and there\nhoping for rain\nbefore it turns yellow'

poem3 = 'There\nonce\nwas\na\ndragon'

print(pin_extractor([poem, poem2, poem3]))
📤 Output
['5203', '4546', '42210']

🧠 Python Concepts Practiced

This project demonstrates several fundamental Python concepts:

Functions
Lists
for loops
enumerate()
String manipulation
split()
Conditional statements (if/else)
len()
String concatenation
Multiline strings
🔎 Key Python Functions
split()
poem.split('\n')

Splits the poem into separate lines.

line.split()

Splits a line into individual words.

enumerate()
for line_index, line in enumerate(lines):

Provides both the index and the value while looping through the lines.

len()
len(words[line_index])

Returns the number of characters in the selected word.

🎯 Purpose

This project is a beginner-friendly exercise in Python string processing, loops, lists, and conditional logic. It demonstrates how text can be processed to generate a simple code based on predefined rules.

👩‍💻 Author

Hashini Konara

Built as part of my Python learning journey.
