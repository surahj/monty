# Monty 
Monty 0.98 is a scripting language that is first compiled into Monty byte codes (Just like Python). It relies on a unique stack, with specific instructions to manipulate it. The goal of this project is to create an interpreter for Monty ByteCodes files.

# Description
Our monty works as a interpreter for Monty ByteCodes files. Files containing Monty byte codes usually have the .m extension. Most of the industry uses this standard but it is not required by the specification of the language. There is not more than one instruction per line. There can be any number of spaces before or after the opcode and its argument:
#  Installing and Using
Clone the repository into a new directory:

``` https://github.com/surahj/monty.git ```

Compile with the following:

``` gcc -Wall -Werror -Wextra -pedantic *.c -o monty ```

Run the interpreter on a file:

``` ./monty file.m ```

# Monty Opcodes
| Opescode | Description |
| -------- | ----------- |
| push | Push an element to the stack. |
| pall | 	Prints all the values on the stack, starting from the top of the stack.|
| pint | Prints the top value of the stack/queue.|
| pop | Removes the top element of the stack/queue. |
| swap | Swaps the top two elements of the stack/queue. |
| nop | Does not do anything. |
| add | Adds the top two elements of the stack/queue.
The result is stored in the second element from the top and the top element is popped.|



