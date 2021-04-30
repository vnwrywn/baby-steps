# Bash Scripting <!-- omit in toc -->

Bash scripting is making a series of commands in a plain text file called bash scripts. The goal of
bash scripting is to make everyday routine less tedious to perform.

## Table of Contents <!-- omit in toc -->

- [Variables](#variables)
  - [Special variables](#special-variables)
- [Input](#input)
- [Operations](#operations)
  - [let](#let)
  - [expr](#expr)
  - [Double parentheses](#double-parentheses)
  - [Length of a variable](#length-of-a-variable)
- [Conditionals](#conditionals)
  - [If statements](#if-statements)
  - [Case Statements](#case-statements)
  - [Test](#test)
  - [Boolean Operations](#boolean-operations)
- [Loops](#loops)
  - [While loops](#while-loops)
  - [Until loops](#until-loops)
  - [For loops](#for-loops)
  - [Break and continue](#break-and-continue)
  - [Select](#select)
- [Funtions](#funtions)
  - [Local variable](#local-variable)
  - [Overriding commands](#overriding-commands)

## Variables

A variable is a temporary store for a piece of information. There are two operation that can be performed
on a variable; setting and reading the value of a variable. A variable is read and reffered by placing a
"$" sign before the name of the variable. A variable may be placed in anywhere in a script, in which it
will be replace by its value when the script is run.

### Special variables

- $0 -> The name of the Bash script.
- $1 - $9 -> The first 9 arguments to the Bash script. (As mentioned above.)
- $## -> How many arguments were passed to the Bash script.
- $@ -> All the arguments supplied to the Bash script.
- \$? -> The exit status of the most recently run process.
- \$$ -> The process ID of the current script.
- $USER -> The username of the user running the script.
- $HOSTNAME -> The hostname of the machine the script is running on.
- $SECONDS -> The number of seconds since the script was started.
- $RANDOM -> Returns a different random number each time is it referred to.
- $LINENO -> Returns the current line number in the Bash script.

## Input

Most scripts will require inputs to perform their designated tasks. These inputs will then be assigned as
a value of a variable or used right away. The following command will assign the input to a variable
named var.
>read var

## Operations

An arithmetic operations is often an integral part of our daily routine.

### let

Allows simple arithmetic operations.

>let <"arithmetic expression">

- \+ -> performs additions
- \- -> performs substractions
- \\* -> performs multiplications
- / -> performs divisions
- ++ -> performs increment
- -- -> performs decrement
- % -> returns modulus

e.g:

```bash
let "var = 1 + 1"
echo $var ## 2
let var++
echo $var ## 3
```

### expr

Similiar to let, but prints the result instead of assigning it to a variable

>expr item1 operator item2

e.g:

```bash
expr 1 + 1 ## 2
var=$( expr 2 + 2 )
echo $var ## 4
```

### Double parentheses

Similiar to let.

>$(( expression ))

e.g:

```bash
var=$(( 1 + 1 ))
echo var ## 2
(( var++ ))
echo var ## 3
```

### Length of a variable

Used to get the number of characters a variable has.

>${#variable}

e.g:

```bash
var=11
echo ${#var} ## 2
```

## Conditionals

### If statements

Functions like any other if function

```bash
if [ <some test> ]
then
    <commands>
[elif [ <some test> ]
then
    <different commands>]
[else
    <other commands>]
fi
```

### Case Statements

Again, not much difference from the usual case statements

```bash
case <variable> in
<pattern 1>)
    <commands>
    ;;
<pattern 2>)
    <other commands>
    ;;
esac
```

### Test

The following are operators for test:

- ! EXPRESSION -> The EXPRESSION is false.
- -n STRING -> The length of STRING is greater than zero.
- -z STRING -> The lengh of STRING is zero (ie it is empty).
- STRING1 = STRING2 -> STRING1 is equal to STRING2
- STRING1 != STRING2 -> STRING1 is not equal to STRING2
- INTEGER1 -eq INTEGER2 -> INTEGER1 is numerically equal to INTEGER2
- INTEGER1 -gt INTEGER2 -> INTEGER1 is numerically greater than INTEGER2
- INTEGER1 -lt INTEGER2 -> INTEGER1 is numerically less than INTEGER2
- -d FILE -> FILE exists and is a directory.
- -e FILE -> FILE exists.
- -r FILE -> FILE exists and the read permission is granted.
- -s FILE -> FILE exists and it's size is greater than zero (ie. it is not empty).
- -w FILE -> FILE exists and the write permission is granted.
- -x FILE -> FILE exists and the execute permission is granted.
- *= will do a string comparison, but -eq will do a numarical comparison*

### Boolean Operations

- && -> and
- || -> or

## Loops

### While loops

Regular while loops. You know the drill.

```bash
while [ <some test> ]
do
   <commands>
done
```

### Until loops

Like while loops, but the commands will be executed until the test becomes true

```bash
until [ <some test> ]
do
   <commands>
done
```

### For loops

I'm starting to feel that i don't need to add an explaination for every single thing.

```bash
for var in <list>
do
   <commands>
done
```

Or

```bash
for value in {<int1>..<int2>}
do
   echo $value
done
```

### Break and continue

Yup, like any other break and continue

- break -> stops the looping process
- continue -> stops the current cycle and skips ahead to the next

### Select

Allows you to make a simple menu system

```bash
select var in <list>
do
    <commands>
done
```

## Funtions

```bash
function_name () {
   <commands>
   [return]
}
```

OR

```bash
function function_name {
   <commands>
   [return]
}
```

### Local variable

Used to make a variable only available for a function

>local var_name=<var_value>

### Overriding commands

Overrides a command by creating a method of the same name as the command
e.g:

```bash
ls () {
    command ls -lh
    }
ls ## ls -lh
```
