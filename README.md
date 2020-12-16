# lua-guide
If you'd like to make changes to this, DM Raccoonyz#0001 and I'll probably make you a contributor.
## What is Luau?
Luau is a modified version of [Lua](https://www.lua.org/) used for game development on Roblox. It has some features removed and others added. 
## Making a script on Roblox
Roblox has 3 different types of scripts: Server scripts, local scripts, and module scripts. I'll discuss the differences later, but for now we'll just start off with server scripts.

To create a server script, go into Roblox Studio. Server scripts will run in the workspace, in GUIs, and in ServerScriptService. We'll make one in the ServerScriptService. Go into your Explorer menu (View -> Explorer) and hover over ServerScriptService. Right click on it and then click on `Insert Object...`. Search for just "Script", and click on `Script`. You should now be in the script editor. If you ever leave the script editor you can get back into it by double clicking on the script you want to edit.


![Example](https://cdn.discordapp.com/attachments/427201562293698562/788524366169112576/unknown.png)


To run a script, go to Home -> Play.
## Variables
We will start off with variables. Variables are a key component of programming. They can hold values which is extremely useful. There are 2 types of variables - local and global. I'll explain the differences later. (I know, a lot of promises) You should always use local variables whenever possible for many reasons.

To define a local variable you write the following:

`local nameOfVariable = valueOfVariable`

nameOfVariable is the name of the variable (this is important as it is what you use when you want to use the variable) and valueOfVariable is the value. The value of the variable can be many different things, and those things are data types. I will get into data types in section below.
## Numbers and Strings
Data types are used in function parameters and variables. There are many different data types but the ones I will be focusing are strings and numbers.

Strings can hold all kind of text. Numbers can only hold numbers. 

You can define strings by surrounding the text with either `"` or `'`. For multiline strings you can use `[[` and `]]` but that's never really necessary.

Here's an example.

```lua
local coolString = "Hello world"
local anotherCoolString = 'Hello world'
```
Numbers don't need " or '.
```lua
local coolNumber = 12345
```
You can use numbers in strings though. Keep in mind that strings and numbers will never be equal, even if they have the same value.

## Variables (part 2)
Now that you have learned about data types we can get into variables more. Variables can be used in place of a data type. Here is an example
```lua
local a = 1
local b = a
```
This would make `b` have a value of `1`.
Keep in mind variables cannot be used in strings. 

## Functions
Copy and pasting code over and over can be a pain. Functions are there to fix that! Functions can also be used as parameters in functions.

Functions act like a variable except they can be called upon. Pretty nifty, huh?

Trippy, right? If you are defining a function to be used, you can do one of 2 options. Either:
```lua
local function nameOfFunction(nameOfParam1, nameOfParam2)

end
```
or
```lua
local nameOfFunction = function(nameOfParam1, nameOfParam2)

end
```
After the `function` should be a right facing parenthesis. You can then have a comma list which will be the parameters. Parameters act like variables and can be provided when you call the function. See below:
```lua
local function nameOfFunction(nameOfParam1, nameOfParam2)
  print(nameOfParam1)
  print(nameOfParam2)
end
nameOfFunction("Hello world", "world Hello")
```
That will print `Hello world` followed by `world Hello` into the output.

All the code inside the `function([parameters])` and `end` will be executed when the function is called. The function defining is ended by an `end`. I'll explain more about ends later. To call a function, you do nameOfFunction(value1, value2). You give the values in a list separated by commas. These are then translated in order to the parameters. You don't need to give a function values.

Functions can also return a value. This is marked by using the global `return` function. `return` stops the current function and goes back to what was originally running. It accepts a single value which can be anything. This value makes the function **return** that value. Here's an example.
```lua
local function justReturnsHelloWorld()
  return("Hello world")
end
local helloWorld = justReturnsHelloWorld()
print(helloWorld)
print(justReturnsHelloWorld())
```
That will print `Hello world` twice. Yes, you can use function calls in function parameters themselves:
```lua
local function printWhatIsGiven(printThis)
  print(printThis)
end
local function justReturnsHelloWorld()
  return("Hello world")
end
printWhatIsGiven(justReturnsHelloWorld())
```
That will print Hello world.
## nil

`nil` is very important. It is a data type that acts as Lua's version of null. For example, all variables are nil by default.

An example is if you don't provide a value to a function where the function wants one.

```lua
function giveMeValues(thisWillBeNil)
  print(value)
end
giveMeVaules()
```
That will print `nil`. You can also use nil as a global. 
```lua
function giveMeValues(thisWillBeNil)
  print(value)
end
giveMeVaules(nil)
```
Even though I did provide the function a value, the value was nil, so it still printed nil. 
## Comments
Comments can be used to leave messages in code without interrupting it. There are two types: singular line and multi-line.

Singular line comments are started by typing --. They then make everything on that line following it a comment. Here's an example.
```lua
local var = "Hello!" -- Here's a comment!
```
Multi-line comments are started by --\[\[ and ended with a ]]. These turn everything between the --\[\[ and the ]] into a comment.
```lua
local var = --[[Here's a multi-line comment!]] "Hello"
```
```lua
--[[
Multiple lines
are great!
]]
local var = "Hello"
```
From now on I will be showing expected outputs by doing --> \[output] after the print.
## end
Many things in Lua will require you to provide code in order to run. An example would be functions. But how do you tell Lua when the code is over? `end` is there for you.

Here is an example of using `end` in a function:
```function endThis()

end -- An end is here
```
Confused? I get you. Here's an example showing the function and the end. Everything to the right of the `|` is the code that will be run when the function is called.
```lua
-- This code won't actually work, it's just an example
function endThis() 
| print("Hi!")
| print("Hello!")
|
|
end -- An end is here
```
In the case that you have nested code (functions inside functions, loops inside loops, etc), the end will end the one that is closest above. Here is an example. I marked which one connects to each.
```lua
function func() -- (B)
function func2() -- (A)

end -- (A)
end -- (B)
```
## if and booleans
`if` lets you run code based on whether or not a statement is true or false. If the statement is true, it will run. If not, it won't. The format is this:
```lua
if booleanStatement then

end
```
You can also use elseif and else. 

`else` runs if the boolean statement is false. It acts like an end except that it will only end the `if` statement it is connected to. It looks like this:
```lua
if booleanStatement then

else

end
```
`elseif` act like a mix of an if and an else. Here is an example.
```lua
if booleanStatement then

elseif booleanStatement2 then

end
```
`elseif`s will only run if the `if` statement is `false`, even if the `elseif` statement is `true`. You can have as many `elseif`s as you'd like, but only 1 else. You can also have `elseif`s and an `else`!
```lua
if booleanStatement then

elseif booleanStatement2 then

else

end
```
Now for booleans. Booleans are statements that either equate to `true` or `false`. Booleans have certain signs that dictate what kind of operation you are doing (see below).
Symbol | Name | Example (will be true)
------------ | ------------- | -------------
== | Equal to                 | 1 == 1
~= | Not equal to             | 1 ~= 2
\>  | Greater than             | 2 \> 1
<  | Less than                | 2 < 1
\>= | Greater than or equal to | 2 \>= 1
<= | Less than or equal to    | 1 <= 1

Here is an example of a boolean statement in an `if` statement:
```lua
if 1 == 1 then
  print("Math works!") --> Math works!
else
  print("Math is broken") -- Won't print because 1 == 1 is true
end 
```
There are 3 operators you can use in booleans; `and`, `or`, and `not`. These modify the normal value of the boolean.

`and` will compare the boolean statements to the left and right. If both of them are true the entire statement will be true, otherwise it will be false.
`or` will compare the boolean statements to the left and right. If one or more are true the entire statement will be true, otherwise it will be false.
`not` will turn the statement to the right the opposite of what it was. True becomes false and vice versa.

Here is an example of all of them.
```lua
if 1 == 1 and 2 == 1 then
  print("Hello broken world") -- This won't print because while 1 == 1 is true, 2 == 1 is false.
end
if 1 == 1 or 2 == 1 then
  print("Hello working world") -- This will print because 1 == 1. The 2 == 1 is ignored.
end
if not (1 == 1) then
  print("Hello broken world") -- This won't print because the opposite of true is false, and 1 == 1 is true.
end
```
## Tables
Lua also introduces the table type, which has 2 parts: dictionary part and array part. The array part is an ordered collection of values. Think of it like a list. The dictionary part is an unordered collection of keys to values.

Example of an array:
```lua
local letters = { "a", "b", "c" }
```
It is constructed with curly braces, then each *element* is separated by a comma or a semicolon. When you want to access something from the array you use square brackets and the position of the item you want to get:
```
local secondLetter = letters[2]
print(secondLetter) --> "b"
```
In other languages 0-based indexing is used, so `array[0]` would give you `"a"`, `array[1]` would give `"b"`, and so on. However, Lua uses 1-based indexing, so `array[1]` gives `"a"` and so on.

You can also get the length of a table's array part using the unary `#` operator:
```lua
print(#letters) --> 3
```
Now an example with a dictionary.
```lua
local swordData = {
    damagePerSwing = 10,
    durability = 50
}
```
The difference here is that the dictionary part of a table has no notion of order. This will make sense when we get to generic for loops. Also, you can see we can use a more descriptive index. `damagePerSwing` and `durability` are keys mapped to the values 10 and 50. If we need the number 10 for example from the table we can access it doing `swordData.damagePerSwing`.
```
print(swordData.damagePerSwing) --> 10
```
Also keep in mind that the length operator does not take into account the length of a table's dictionary part.
