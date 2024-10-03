# headerFunctions

## colorText(string: text, string: foregroundColor, string: backgroundColor)
This function takes in a text string and uses ANSI escape codes to change the color of the text. To do this the function takes in 2 or 3 inputs.
- Input $1 is the text to modify the color of
- Input $2 is the foreground color and all of the following are valid choices:
	- black
	- green
	- blue
	- cyan
	- darkGrey
	- lightGreen
	- lightBlue
	- lightCyan
	- red
	- brown
	- magenta
	- lightGrey
	- lightRed
	- yellow
	- lightMagenta
	- white
- Input $3 is the background color and the following are valid choices:
	- black
	- red
	- green
	- yellow
	- blue
	- magenta
	- cyan
	- lightGrey

This function echos back the modified text following processing, to directly print the text following processing, it is recommended to do one of the following depending on need:
``` bash
printf "$(colorText $1 $2 $3)\n"
  echo $(colorText $1 $2 $3)
```
### Debugging Flag
Set to TRUE in order to get color related errors.

This by default is set to false and when the function detects an invalid input, the text is set to default colors to minimize impact. The foreground color is set to light grey and the background color is set to be nothing. It should be noted that the foreground and background colors are validated individually. When set to true, if an invalid color is determined, an error message is printed to the console giving what the wrong input was.

## bar(char: characterToRepeat, boolean: newLineCharacter, int: customWidth)
bar() takes in 1 required input and up to 2 option inputs

The purpose of this function is to print out a character across the width of the current terminal window
- Input $1 (String) is the character to be printed. Requires exactly 1 character and there is internal validation for this
- Input $2 (boolean) determines whether to add a trailing new line character or not after the bar of characters has been printed. Defaults to TRUE
- Input $3 (int) is an optional input if a custom width is needed that isn't the width of the current terminal window. When not set or set to 0, the function will default to the Terminal Width
