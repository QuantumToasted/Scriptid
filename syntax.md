# scriptid syntax
Below are some syntax rules for scriptid. This file will be considered pretty volatile until a much more solid definition of proper syntax.

### Basic basics
Scriptid uses C-style syntax for most things:
* Brackets (`{` `}`) are used to define scopes.
* Assignments or modifications must end in a semicolon (`;`).

### Comments
Comments are very simple. `#` anywhere on a line treats the rest of the line as a comment.

Multi-line comments are not supported.
```py
# This is a comment.
```

### Typing and data types
Scriptid is a statically and strongly-typed language. 

All variables must have their data type specified before assignment, and variables cannot switch from one type to another.

Scriptid has three main basic data types:
#### num
Whole numbers, similar to the `int` type in C#. Expected range: `-2,147,483,648` to `+2,147,483,647`.

Most integer arithmetic operators are supported.
```py
# Assigns the value 5 to num1.
num num1 = 5;

# Note: after being assigned once, the type name is no longer necessary;
num1 = 10;

# Adds 1 to num1.
num1 = num1 + 1;
num1 += 1;
num1++; # Assigns new value to num1 after use
++num1; # Assigns new value before use

# Subtracts 1 from num1;
num1 = num1 - 1;
num1 -= 1;
num1--; # Assigns new value to num1 after use
--num1; # Assigns new value before use

# Multiplies num1 by 5
num1 = num1 * 5;
num1 *= 5;

# Divides num1 by 5
num1 = num1 / 5;
num1 /= 5;

# Provides the remainder after dividing num1 by 3.
# Similar to C#'s remainder (%) operator.
num1 = 10;
num1 = num1 % 3; // Produces 1. 10 / 3 is 3 with a remainder of 1.
num1 %= 3; // Same as above, assuming num1 was 10 again.
```

#### str
Strings, used to represent text. Supports Unicode escape sequences such as \n.

Strings can be defined in one of two ways.
The two following strings are equal to each other.

```py
# "Normal" definition: Text between two quotes. Inline quotes must be escaped with a backslash (\).
# Newlines must be represented with \n - newlines directly in the string are a syntax error.
str str1 = "Hello, and welcome to \"scriptid\"! It's *the* scripting language for your bot!";

# Non-escaped definition. Text between two sets of triple quotes (""") separated by newlines. 
# Any text between the quotes is treated literally, including newlines.
# The only exception is the backslash (\), which is used to split a long single line into two shorter ones.
str str2 = """
Hello, and welcome to "scriptid"! It's *the* \
scripting language for your bot!
""";
```

#### embed
Discord embed message object - not just an embed! It also supports normal plain text as well.

Represented as a JSON object. ~~There will be documentation on the proper format of the `embed` object in the future.~~

```py
# An embed message object with a description and color
embed embed1 = {
  "description": "This is a description, I think.",
  "color": 16711680 # hex FF0000
}
```

This will result in the following embed:

![Embed example](https://i.imgur.com/wWviPER.png)


### Global variables
Global variables are variables which are meant to be shared across all your guild's scriptid scripts.

They are likely to be used for counting the number of times a command has been run, for example.

They are defined with the keyword `using TYPE name;`.

You **must** define your global variable(s) before using them, just like any other variable.

It's recommended to define global variables before the rest of your script, like so:
```py
# Defines or assigns to the global variable 'counter'.
# If this guild does not have a 'counter' variable yet, it will be created.
# DO NOT ASSIGN TO THE VARIABLE HERE. If you wish to assign to a global variable after defining it,
# it must be done in a separate line.
using int counter;

# Assigns to global variable.
counter = 5;
```


##### WIP
