# VIM Cheat Sheet  
A cheat sheet I have produced while learning how to use the almighty editor  
  
## Modes  
  
Esc - Normal Mode (default)  
i - Insert Mode  
(modifier)v - Visual mode  
R - Replace mode (just like hitting the Insert key on the keyboard)  
  
## Navigation  
  
h - left  
j - down  
k - up  
l - right  
  
0 - go to the beginning of line  
$ - go to the end of line  
  
w - go to beginning to next word  
b - go to beginning of previous word  
e - go to end of next word  
  
{ - go to previous paragraph  
} - go to next paragraph  
  
% - go to matching parenthesis/bracket  
  
## Modifying text  
  
i - insert before current Char  
I - insert before current line  

a - append after current letter  
A - append at the end of current line  

o - insert starting at a new line after the current one  
O - insert starting a new line before current one  
  
r - replace current char with another  

cc - delete current line and enter insert mode  
cw - delete current word and enter insert mode  
c$ - delete until end of line and enter insert mode  

## Deleting text  
  
x - delete current char  
X - delete previous char (backspace)  
  
dd - delete current line  
dw - delete a word (from cursor)  
diw - delete a word (from beginning of word)  
  
d$ - delete everything until the end of line  
d0 - delete everything until beginning of line  
  
## Copying text  
  
y - yank (copy)  
yy - copy line  
yw - copy word (from beginning of cursor)  
yiw - copy word (from beginning of word)  
y (during visual mode) - copy highlighted text  
  
p - paste the yanked buffer  
  
  
## Undo/Redo  
  
. (dot) - redo previously performed command  
u - undo previously performed command  

## Indenting

\>\> - indent line  
\<\< - reindent line  

## Searching

/ - forward search  
? - backward search  

n - go to next found occurence  
N - go to previously found occurence  

## Search & Replace

%s - sed through all file  
{num},s - sed from {num} line forward  
,{num}s - sed from beginning of file until {num}  
{num1},{num2}s - sed from {num1} line to {num2} line  

format: {range}s/{search-term}/{replace-term}/{options}  
NOTE: {search-term} can be regex  

possible {options}:  
g - match multiple times on a single line  
c - ask before replacing  

## Performing external commands

:!{external command} - executes command and returns to vim after execution  
:r!{external command} - read the result of external command and put it under cursor  
:{num1},{num2}! {command} - replace the contents of the file between line {num1} and {num2} with result of external command.  
                            Feed as input the contents between those lines.  

## Saving/exiting files

:q - quit without saving  
:w - save without exiting  
:x - save and exit  
:saveas {file} - save changes to {file}  

ZZ - save and exit  

## Performing a command n times  
  
Every command can be performed several times by supplying it with a number  
  
e.g. **4iHello There\n** results in:  
> Hello There  
> Hello There  
> Hello There  
> Hello There  
  
Similarly, you can do the same for shortcuts such as [x, u, r...].  
The only exception is the d shortcut (delete).  
  
For it, you have to supply the number **after** the command. Also, you have to specify a direction for deleting by using the arrow keys.  
  
e.g. **d4(right)** will delete the next 4 characterx starting from the cursor.  
  
e.g. **d4$** will delete the next 4 lines.  

## Extra Tips & Tricks

### Quick Navigation
gg - go to first line of file
G - go to last line of file
{number}G - go to specific line number
Ctrl+f - page down
Ctrl+b - page up
Ctrl+d - scroll down half page
Ctrl+u - scroll up half page

### Advanced Editing
J - join current line with next line
gU{motion} - make text uppercase (e.g. gUw for word)
gu{motion} - make text lowercase (e.g. guiw for inner word)
~ - toggle case of character under cursor
Ctrl+a - increment number under cursor
Ctrl+x - decrement number under cursor

### Visual Mode Tips
v - character-wise visual mode
V - line-wise visual mode
Ctrl+v - block visual mode (column selection)
gv - reselect last visual selection
o - move to other end of selection

### Working with Registers
"ay - yank into register 'a'
"ap - paste from register 'a'
"+ - system clipboard register
:reg - view all registers

### Marks & Jumps
ma - set mark 'a' at current position
'a - jump to line of mark 'a'
`a - jump to exact position of mark 'a'
'' - jump back to last position
Ctrl+o - jump to previous location
Ctrl+i - jump to next location

### Macros
qa - start recording macro into register 'a'
q - stop recording macro
@a - execute macro from register 'a'
@@ - repeat last executed macro

### Window Management
:split or :sp - horizontal split
:vsplit or :vsp - vertical split
Ctrl+w w - switch between windows
Ctrl+w h/j/k/l - navigate to window in direction
Ctrl+w = - make all windows equal size
Ctrl+w _ - maximize current window height
Ctrl+w | - maximize current window width

### Useful Settings
:set number - show line numbers
:set relativenumber - show relative line numbers
:set ignorecase - case insensitive search
:set smartcase - case sensitive if uppercase used
:set hlsearch - highlight search results
:noh - clear search highlighting

### File Navigation
:e {filename} - open file for editing
:bn - next buffer
:bp - previous buffer
:ls - list all buffers
gf - go to file under cursor
