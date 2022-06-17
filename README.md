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
| add | Adds the top two elements of the stack/queue. The result is stored in the second element from the top and the top element is popped.|
| sub | Subtracts the top element of the stack/queue from the second element from the top. The result is stored in the second element from the top and the top element is removed. |
| mul | Multiplies the top two elements of the stack/queue. The result is stored in the second element from the top and the top element is removed. |
| div | Divides the second element from the top of the stack/queue by the top element.The result is stored in the second element from the top and the top element is removed. |
| mod | Computes the modulus of the second element from the top of the stack/queue divided by the top element. The result is stored in the second element from the top and the top element is removed. |
| pchar | Prints the character value of the top element of the stack/queue. The integer at the top is treated as an ASCII value. |
| pstr | Prints the string contained in the stack/queue. Prints characters element by element until the stack/queue is empty, a value is 0, or an error occurs. |
| rotl | Rotates the top element of the stack/queue to the bottom. |
| rotr | Rotates the bottom element of the stack/queue to the top. |
| stack | Switches a queue to stack mode. |
| queue | Switches a stack to queue mode. |
| # | Opcodes preceeded by a # are treated as comments and the corresponding line is ignored. |

# Examples
Note, Monty Interpreter runs in the default mode of STACK mode. Meaning it uses a stack. To switch to queue mode, see examples below.

Push values onto the stack and print them all, or the top of the stack/front of queue.

```
$ cat push_pall_pint.m
push 1
push 2
push 3
pall
pint
$ ./monty push_pall_pint.m
3
2
1
3
```

Using mathmatical operations to add, multiply, divide, etc. Takes the second from the top and performs the operation on the top: second_from_top / top, second_from_top - top, etc. Then assigns that to the second_from_top and pops the top element off the stack.

```
$ cat math.m
push 3
push 2
push 1
pall
mul
pall
$ ./monty math.m
1
2
3
1
6
```

Entering queue mode to perform all operations in FIFO (queue) mode instead of default LIFO (stack) mode. Note: does not change current stack, sets front of queue to top of stack.

```
$ cat queue.m
queue
push 1
push 2
push 3
pall
stack
push 4
push 5
push 6
pall
$ ./monty queue.m
1
2
3
6
5
4
1
2
3
```









