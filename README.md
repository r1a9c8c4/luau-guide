# lua-guide
## What is Luau?
Luau is a modified version of [Lua](https://www.lua.org/) used for game development on Roblox. It has some features removed and others added. 
## Making a script on Roblox
Roblox has 3 different types of scripts: Server scripts, local scripts, and module scripts. I'll discuss the differences later, but for now we'll just start off with server scripts.

To create a server script, go into Roblox Studio. Server scripts will run in the workspace, in GUIs, and in ServerScriptService. We'll make one in the ServerScriptService. Go into your Explorer menu (View -> Explorer) and hover over ServerScriptService. Right click on it and then click on `Insert Object...`. Search for just "Script", and click on `Script`. You should now be in the script editor. If you ever leave the script editor you can get back into it by double clicking on the script you want to edit.

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
```
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

`nil` is very important. It act as Lua's version of null. If it doesn't exist, it's probably nil.

An example is if you don't provide a value

## Comments

## if and booleans

## Tables and Dictonaries
