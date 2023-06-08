# Basic Syntax and Data Types

LUA is a lightweight and easy to learn programming language. In this section, we will cover the basic structure of a LUA script, as well as the different data types available and how to manipulate them.

## Script Structure
A LUA script is a plain text file with the `.lua` file extension. The script is executed from top to bottom, and it can contain a combination of statements, comments, and functions.

### Statements
Statements are commands that perform a specific action, such as assigning a value to a variable or calling a function. 

-- This is a statement that assigns the value "hello" to the variable "greeting"
greeting = "hello"

### Comments
Comments are used to add notes or explanations to the code and are ignored by the interpreter. In LUA, comments are created using double dashes (`--`).
```lua
-- This is a comment and will be ignored by the interpreter
greeting = "hello"
```
### Functions
Functions are blocks of code that perform a specific task and can be reused throughout the script. Functions are defined using the `function` keyword and are called using their name followed by parentheses (`()`).
```lua
-- This is a function that prints a greeting message
function sayHello()
    print("Hello!")
end

-- This is how the function is called
sayHello()
```

## Data Types
LUA supports several data types, including:

### Numbers
Numbers are used to represent numeric values and can be integers or floating-point numbers.
```lua
-- This is a number
age = 25

-- This is also a number, but with a decimal point
price = 9.99
```
### Strings
Strings are used to represent text and are enclosed in double or single quotes.
```lua
-- This is a string
name = "John"

-- This is also a string
address = '123 Main St'
```
### Booleans
Booleans are used to represent true or false values.
```lua
-- This is a boolean
isValid = true

-- This is also a boolean
isCompleted = false
```
### Tables (see 6. Tables and Metatables)
Tables are used to store collections of values and can be used as arrays or dictionaries.
```lua
-- This is a table
myTable = {1, 2, 3}

-- This is also a table, but with named keys
myDictionary = {name = "John", age = 25}
```
### Manipulating Data
LUA provides several built-in functions and operators for manipulating data, such as concatenating strings, performing mathematical operations, and more.
```lua
-- Concatenating strings
greeting = "Hello, " .. "world!"

-- Performing mathematical operations
sum = 2 + 2
difference = 10 - 5
product = 2 * 3
quotient = 10 / 2
```

?> This is just a small introduction to LUA basic syntax and data types, there is much more to learn and explore, such as control structures, libraries and modules, OOP and more.

!> Please keep in mind that the code snippets will not run as it is and it is intended to be used as an example and reference.


# Variables and Functions

In LUA, variables are used to store and manipulate data, and functions are used to organize and reuse code.

## Variables
In LUA, variables are declared using the `local` keyword or without it.
```lua
-- Declaring a variable
local x = 5

-- Declaring a variable without the `local` keyword
y = 10
```
It's recommended to use the local keyword when declaring a variable, as it limits the scope of the variable to the current function or file, and prevents accidental global variable assignments.

LUA supports several data types, including numbers, strings, booleans, and tables.
```lua
-- Declaring a number variable
local age = 25

-- Declaring a string variable
local name = "John"

-- Declaring a boolean variable
local isValid = true

-- Declaring a table variable
local myTable = {1, 2, 3}
```
## Functions
In LUA, functions are declared using the function keyword and can be called using the function name followed by parentheses.
```lua
-- Declaring a function
function sayHello()
    print("Hello!")
end

-- Calling a function
sayHello()
```
Functions can also take parameters and return values.
```lua
-- Declaring a function with parameters
function add(x, y)
    return x + y
end

-- Calling a function with arguments
result = add(5, 10)
```
Functions can be stored in variables and passed as arguments to other functions.
```lua
-- Storing a function in a variable
local myFunction = function()
    print("Hello!")
end

-- Passing a function as an argument
otherFunction(myFunction)
```
This is just a small introduction to variables and functions in LUA, there is much more to learn and explore, such as closures, recursion, and more.

# Flow Control

In LUA, flow control statements are used to control the flow of execution of a script. These include `if`, `else`, `elseif`, `for`, `while`, and `repeat` statements.

## If-Else Condition
The `if` statement is used to check if a certain condition is true and execute a block of code if it is. The `else` statement is used as an alternative if the condition is not true.
```lua
-- If-else statement
local x = 5
if x > 10 then
    print("x is greater than 10")
else
    print("x is less than or equal to 10")
end`
```
## Elseif Condition
The `elseif` statement is used to check multiple conditions. If the first condition is not true, the script will check the next one, and so on, until a true condition is found or the end of the script is reached.
```lua
-- Elseif statement
local x = 5
if x > 10 then
    print("x is greater than 10")
elseif x < 0 then
    print("x is less than 0")
else
    print("x is between 0 and 10")
end`
```
## For Loop
The `for` loop is used to iterate over a range of numbers or elements in an array or table. The loop variable is declared and initialized before the loop, and the loop will continue until the end condition is met.
```lua
-- For loop
for i = 1, 10 do
    print(i)
end`
```
## While Loop
The `while` loop is used to execute a block of code repeatedly as long as a certain condition is true.
```lua
-- While loop
local x = 5
while x > 0 do
    print(x)
    x = x - 1
end
```

## Repeat Until
The `repeat` statement is used to execute a block of code repeatedly until a certain condition is met. The code block is executed at least once before the condition is checked.
```lua
-- Repeat until
local x = 5
repeat
    x = x - 1
    print(x)
until x == 0
```
The above code snippet will execute the loop until x is equal to 0, and the value of x will be decremented in each iteration.

!> Please keep in mind that the code snippets will not run as it is and it is intended to be used as an example and reference.

# FiveM Specific Functions

In FiveM, a modification for the popular game Grand Theft Auto V, there are several functions that are specific to the FiveM platform that you can use in your scripts.

Use the natives reference to find the list of all available functions : https://docs.fivem.net/natives/

## Registering a Command
To register a command that can be executed in the chat, you can use the `RegisterCommand` function.
```lua
-- Registering a command
RegisterCommand("hello", function()
    print("Hello!")
end, false)
```
The first argument is the command name, the second argument is the callback function that will be executed when the command is called, and the third argument is the "restricted" boolean : If this is a server command and you set this to true, then players will need the `command.yourCommandName` ace permission to execute this command
## Triggering an Event
To trigger an event that can be handled by other scripts, you can use the TriggerEvent function.

```lua
-- Triggering an event
TriggerEvent("myEvent", "Hello, World!")
```
The first argument is the event name, and the following arguments are passed to the event handlers.

## Registering an Event
To register an event handler, you can use the AddEventHandler function.

```lua
-- Registering an event handler
AddEventHandler("myEvent", function(message)
    print(message)
end)
```
The first argument is the event name, and the second argument is the callback function that will be executed when the event is triggered.

## Getting the Player's Position
You can use the GetEntityCoords function to get the player's current position in the world.

```lua
local coords = GetEntityCoords(PlayerPedId())
-- coords is a vector3 object, to access the specific value (x, y, or z), you have to see the vector3 as a table
print(coords.x) -- X
print(coords.y) -- Y
print(coords.z) -- Z
```
The first argument of the function is the player entity

## Creating a Blip
You can use the AddBlipForCoord function to create a blip on the map at a specific position.

```lua
-- Creating a blip
local blip = AddBlipForCoord(x, y, z)
```
The arguments passed to the function are the x, y, and z coordinates of the blip.

## Setting a Blip's Icon
You can use the SetBlipSprite function to set the icon of a blip.

```lua
-- Setting a blip's icon
SetBlipSprite(blip, 1)
```
The first argument is the blip and the second argument is the icon number.

?> This is just a small introduction to FiveM specific functions, there are many more functions, properties, and events you can use in your scripts. Be sure to check the official documentation and resources for more information and examples.

# Best Practices and Tips

When writing scripts for FiveM, it's important to keep in mind some best practices and tips to make sure that your code is clean, readable, and efficient.

## Naming Conventions
It's important to use clear and consistent names for variables, functions, and events. Avoid using abbreviations or single letters, and use camelCase or snake_case depending on your preference.
```lua
-- Good naming
local playerHealth = 100
function checkPlayerHealth()
  -- code
end

-- Bad naming
local plH = 100
function chkPlH()
  -- code
end
```

## Commenting your Code
It's a good practice to leave comments in your code to explain what certain parts of your script do. This makes it easier for other developers to understand and maintain your code.

```lua
-- Commenting your code
function checkPlayerHealth()
  -- Check if player's health is below a certain threshold
  if playerHealth < 50 then
    -- Trigger an event to alert the player
    TriggerEvent("playerLowHealth")
  end
end
```

## Organizing your Code
It's important to organize your code into functions, so that it's easier to read, debug, and maintain. Try to keep each function focused on a specific task and avoid too much nesting or long functions.

```lua
-- Organizing your code
function checkPlayerHealth()
  -- Check if player's health is below a certain threshold
  if playerHealth < 50 then
    -- Trigger an event to alert the player
    TriggerEvent("playerLowHealth")
  end
end

function displayHealthWarning()
    -- Display a warning message to the player
    exports.myUI:showAlert("Your health is low!", "warning")
end

AddEventHandler("playerLowHealth", displayHealthWarning)
```

## Avoiding Global Variables
It's best practice to avoid using global variables as much as possible, as they can cause conflicts and make it harder to track where a variable is being used. Instead, use local variables and pass them as arguments to functions.
```lua
-- Avoiding global variables
local playerHealth = 100

function checkPlayerHealth(health)
  -- Check if player's health is below a certain threshold
  if health < 50 then
    -- Trigger an event to alert the player
    TriggerEvent("playerLowHealth")
  end
end

checkPlayerHealth(playerHealth)
```

## Error Handling
It's important to handle errors in your script to prevent it from crashing or breaking. Use the pcall function to catch errors, and use the error function to display a message to the user.

```lua
-- Error handling
local success, error = pcall(functionThatMightError)
if not success then
  error("An error occurred: " .. error)
end
```
## Performance Optimization
Performance is an important aspect when developing scripts for FiveM. Here are a few tips to keep in mind:
- Try to avoid using loops where possible, especially when working with large data sets.
- Use the appropriate data types for variables and try to avoid unnecessary type conversions.
- Avoid using too many nested if-else statements, as they can affect the performance of your script.

By following these best practices and tips, you can ensure that your scripts are well-organized, efficient, and easy to maintain. It's important to keep in mind that these are general guidelines and there may be exceptions to them. However, following these guidelines will help you to write clean, readable, and effective code.

# Tables and Metatables

In Lua, tables are a fundamental data structure used to store and organize data. A table is a collection of key-value pairs, where each key is unique within the table. Tables can be used as arrays, dictionaries, objects, or a combination of these.

## Creating a Table
To create a table, you can use curly braces `{}` and separate the key-value pairs with commas. Keys can be either numbers or strings, and values can be any Lua data type, including other tables.

```lua
-- Creating a table
local myTable = {
    ["name"] = "John",
    ["age"] = 25,
    [3] = "hello",
    -- Tables can be used as values of other tables
    ["nestedTable"] = {
        ["key"] = "value"
    }
}
```

In this example, the table myTable has four key-value pairs. The first key "name" has the value "John", the second key "age" has the value 25, the third key 3 has the value "hello", and the fourth key "nestedTable" has another table as its value.

## Accessing Table Elements
You can access the elements of a table using the table name followed by the key in square brackets `[]`.

```lua
-- Accessing table elements
print(myTable["name"]) -- Output: John
print(myTable.name)     -- Output: John
print(myTable[3])      -- Output: hello
print(myTable.nestedTable.key) -- Output: value
```
## Metatables

Metatables are used to define the behavior of a table when certain operations are performed on it. A metatable is a table that can be set as the metatable of another table. The metatable contains metamethods, which are functions that define the behavior of the table when certain operations are performed on it.

```lua
-- Creating a metatable
local myMetatable = {
    __add = function(table1, table2)
        local newTable = {}
        for k, v in pairs(table1) do
            newTable[k] = v
        end
        for k, v in pairs(table2) do
            newTable[k] = v
        end
        return newTable
    end
}

-- Setting the metatable
setmetatable(myTable, myMetatable)

-- Using the metamethod
local myOtherTable = {
    ["city"] = "New York",
    ["country"] = "USA"
}
local myCombinedTable = myTable + myOtherTable
print(myCombinedTable.name)     -- Output: John
print(myCombinedTable.city)     -- Output: New York
```

In this example, the `__add` metamethod is defined to combine two tables into a new table. The setmetatable function is used to set `myMetatable` as the metatable of myTable. Finally, the `+` operator is used to combine `myTable` and `myOtherTable` into `myCombinedTable`.

Please keep in mind that the code snippets will not run as is and are intended to be used as examples and references.



# Credits

[Credits To Original Author](https://github.com/Mathu-lmn/fivem-cheatsheets/tree/main)