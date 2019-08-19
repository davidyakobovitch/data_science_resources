These notes provide a summary of capabilities with Vim.
<br>

###### Insert Mode
```bash
i # Enter Insert Mode from Normal Mode
Escape # Exits Insert Mode and enters Normal Mode
```

###### Command Mode - [count]operation{motion}
```bash
j # Move down a line 
k # Move up a line
l # Move to the right
h # Move to the left
Ctrl + F # Page down or forward
Ctrl + B # Page up or backward
w or b # Move forward or backward a word
W or B # Move forward or backward a word with white space as word boundary
1gg or gg # Move to the first line of a file
27gg or 27G # Move to the 27th line
$G or G # Move to last line of file
Ctrl + G # Shows how far you are in a file 
g + Ctrl + G # Shows how you are in file by characters
^ # Jump to the first character in a line
0 # Move to the beginning of a line
$ # Jump to the end of a line
x # Deletes character to the right
X # Deletes character to the left
dw # Deletes word to the right 
dl # Delete letter to the right
dh # Delete letter to the left
dj # Deletes the current line and the line below it
dk # Deletes the current line and the line above it
d0 # Delete from current position to the beginning of the line
D or d$ # Delete from current position to the end of the line
dd # Deletes current line no matter where cursor is 
3dd # Deletes current line plus two more lines
3w # Move over 3 word motions
d3w # Delete 3 words 
2d3w # Delete 6 words
) # Jump to start of next sentence
. # Repeats the previous command
```

###### Line Mode
```bash
: # Enters command line mode from normal mode
q! # Quits and exits without saving changes
wq # Writes and quits the file
w # File saved, and placed in normal mode to continue editing
q # Quits vim, only if no changes made
32 # Move to line 32
$ # Move to the last line in the file
set ruler! # Toggles ruler on and off
```
