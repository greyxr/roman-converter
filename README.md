# roman-converter
Time spent coding: 3 hours, 50 minutes

The program starts by asking for the type of conversion wanted. If '1' is entered, it then prompts you for an integer, and then prints the Roman numeral equivalent before showing the menu again. If '2' is entered, it prompts you for a string of Roman numerals, and then prints the corresponding integer total before showing the menu again. If '3' is entered, or any other integer, the program quits.

## Overview
  - Function implentation
  - Improvements

## Functions

### main:
Main doesn't do much here. It declares the integers, type, and roman variables, and then has a loop that runs getInput until it returns false.

### getInput:
Takes as input a string "roman" by reference and an integer "integers" by reference.
This function uses a switch statement to create a menu. It takes input to find the type of conversion the user wants, and then takes input
to get the appropriate string or integer. It then calls the appropriate function and outputs the converted string or integer. It returns true if the user
wanted to convert something (so the loop in main is repeated) or false if the user wants to quit or gives an invalid integer as an input.
 
 INPUT SANITIZATION: If I had more time, I would implement error checking to make sure the input is valid. I kept running into bugs and I don't have enough time to get it working.
 
### romanToInt:
Takes as input a string "roman" by reference.
This function uses a map of valid Roman numerals mapped to their corresponding integer value. Each character in the input string is found in the map, and
if it's smaller than the character following it, it should be subtracted from the total. If it's bigger or equal, we add it
to the total. Once we reach the end of the string, we add the last character and return the total.
 
### intToRoman:
Takes as input an integer "n" by reference.
This function will keep subtracting the value of the biggest possible Roman numeral(s) from the input
string (and add that/those Roman numeral(s) to the returning string) until we reach 0. Then, we return the resulting string.
 
 ### checkLargest:
Takes as input an integer "n" by reference.
This function uses two arrays, holding strings of Roman numerals and values of those numerals. There are only 6 valid
instances of subtractive notation for Roman numerals, so I just added those strings to the arrays. This function returns the
string of Roman numeral(s) associated with the largest value smaller than the input integer. If I had more time, I would
change the map used in the romanToInt function to accept strings instead of just characters, so I could reuse it here,
but I kept running into errors.
 
## Improvements

### Input checking

I spent a lot of time trying to sanitize my inputs so that the program could have some level of error checking. I wasn't sure how much I could use Google to remember how to use getline and cin.ignore to flush the input stream if the user put in bad input, so I erred on the side of caution and tried to do it from the documentation. Unfortunately I couldn't figure it out in time, but if I had more time, I would use getline to make sure both integer inputs in getInput are valid. If the inputs aren't valid, it would display a message and loop that section of the getInput function until the user puts in a valid input.

For the Roman numeral input, I would add in checking to make sure the input is a valid Roman numeral. I would do that through looping over the input string and making sure that every
time a character is smaller in value than the next character in the input, that it was a valid use of subtractive notation. It would also check if any of the characters aren't valid Roman numerals.

### Command line arguments

I also spent a while trying to add command line arguments to the program, so that the program would automatically detect the type of input and convert it accordingly. I couldn't figure out how to check the data type of the command line argument, so I eventually took that out, but if I had more time, I would add that in using an if else statement.

### Getting rid of the menu

The biggest change I would make would be getting rid the switch case menu. I tried making the program detect the type of input automatically, set the "roman" or "integers" variable accordingly, and run the appropriate function instead of having to press '1' or '2' every time you want to make a conversion. I couldn't figure out how to detect the data type of the input, but if I had full access to Google it should be pretty simple to implement.
