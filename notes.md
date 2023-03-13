# [pluralsight - ruby 2 foundations](https://app.pluralsight.com/library/courses/ruby-fundamentals/table-of-contents)

---

## 1. INTRO TO RUBY
### installing ruby
- macs have an older version of ruby installd
- install `rvm` via [rvm.io](https://rvm.io/)
- `rvm` works like `nvm` and allows install and management of different versions

```bash
rvm install 3.0.0
rvm install 2.7.7
rvm list
rvm use 3 # =* ruby-3.0.0
```

#### interactive ruby shell
- use for experimentation / exploration
- allows arbitrary ruby code
- works like any other interactive shell

```bash
irb
3.0.0 :001 > # enter ruby code
```

### variables, `nil`, methods, & scope
#### variables
- to create a variable, give it a name and a value
- don't need to declare it beforehand or specify its type
- variable names start with a lowercase letter and use underscores (instead of camelCase)
- to instantiate a variable without a value, can assign `nil`
```ruby
count = 10 # new variable named count wiht a value of 10
result = nil #instantiated the result variable
```

#### nil
- not a primitive, but a special object that signifies no value
- the class is NilClass
- can check if a variable is `nil` by using it's `nil` method `.nil?`
    - the `?` is part of the method name

```ruby
nil.class # NilClass
result = nil # instantiate the variable result with nil
result.nil? # check if the result variable is nil
``` 

#### methods
- in ruby, method names can end with a `?` or `!`
    - `?` is normally used for methods that perform a true/false test
    - `!` is used for methods that do something slightly unexpeted or dangerous (like modifying an object in place instead of returning a modified copy)
        - example: string class, strip method (removed whitespace from both ends)
        - another example: a method that terminates an operation abruptly without firing the normal callbacks
            - normally only define this type of method when they also have a safe count without `!`

```ruby
# .strip does not modify orginal string
a = "  abc  "
a.strip # "abc"
a       # "  abc  ", remains unchanged

# .strip! - different version of .strip to modify a
a.strip! # "abc"
a        # "abc", original string has been modified
```

- defining methods: 
    - use the `def` keyword followed by the method name
    - end the method with the `end` keyword
    - can return value of any time
    - can return values of different types depending on the circumstances
    - methods return the result of evaluating the last expression so no 

```ruby
def double(val)
    val * 2
end
```

- typically, ruby is indented with 2 spaces
- whitespace is not significant unless inside a string
- when calling a method, the `()` around the arguments are option but normally used if there's an argument list and omitted if you don't
- some methods are used like keywords and with those, it's common to omit `()`
    - example: `puts`

```ruby
double("abc")
puts ""
```

#### scope
- methods provide scope for variables
- in the below example, `count` is a local variable so its visibility is limited to the scope it was created in
    - since it's defined at the start of the file, it'll be visible throughout the program
- if a variable is defined within a method then its scope will only be that method
    - the variable will not be visible outside of the method
- if the variable in the method is named the same as the variable outside the method, the method variable shadows the variable created outside of the method. the variable inside the method only exists in the scope of the method and doesn't affect the variable outside of the method.
- global variable: 
    - created with the prefix of `$`
    - visible everywhere throughout the program

```ruby
count = 10

def report
    count = 5
    puts count
end

report      # 5
puts count  # 10

$log_level = "debug" # global variable
```

### flow control, operators, comments
#### flow control
- if/else
    - treats statements as expressions as much as possible
    - the if is an expression which evaluates to the result of the last expression in the selected branch
    - instead of outputting a string in each branch of the if statement, you can set a variable in the if statement and print that
    - can chain assignments as well

```ruby
### original
count = 11

if count > 10
    puts "launching"
else 
    puts "waiting"
end

### refactored
count = 11

message = if count > 10 "launching"
else 
     "waiting"
end

puts message

# chained assignments
a = b = 10
```

#### operators
- comparisons: `>` `>=` `<` `<=` `==` `!=`
- mathematical: `+` `-` `*` `/` `%` `**` (exponent)
- logical: `!` `&&` `||` `not` `and` `or`
- bitwise integer: `&` `|` `^` `~` `<<` `>>`
- assignment: `+=` `-=` `*=` `/=` `%=` `**=` `&=` `|=` `^=` `>>=` `<<=`

#### comments
- `#` 

### useful methods
- `print` outputs a string, used for a prompt
- `gets` waits for your keyboard input and returns it
- `puts` outputs a string combined with the input. `puts` adds a new line to the string.

```ruby
print "enter your name"
name = gets 
puts "your name is " + name
```

- ruby makes it easy to execute a command in another process and collect its result
    - can use backticks (`) to specify a command to execute
- this example, get the time from the system, launched in a separate process and the ruby process will block until it's complete. output of the command is then returned to ruby, stored in a variable, and output. 
- can also use `%x` instead of backticks (`)
- the system method will return true if the command finished with 0 status or false for non-0 status instead of the command output. returns `nil` if the command failed.
- the output of the command is part of standard output, which is why the time is printed twice

```ruby
puts "using backticks:"
res = `time \t`
# res = %xtime \t # using %x
puts res

puts "using system:"
res = system "time \t"
puts res
```


---
## 2. CLASSES & OBJECTS
### creating classes & objects
- 

```ruby

```

### instance variables & methods
- 

```ruby

```

### accessors & virtual attributes
- 

```ruby

```

### initialization & cleanup
- 

```ruby

```

### inheritance
- 

```ruby

```

### class methods & variables
- 

```ruby

```

### method visibility
- 

```ruby

```

### executable class bodies & `self`
- 

```ruby

```

### open classes & monkey patching
- 

```ruby

```

### equality
- 

```ruby

```


---
## 3. FLOW CONTROL
### branching
- 

```ruby

```

### conditional initialization
- 

```ruby

```

### flow control using and/or
- 

```ruby

```

### case statement
- 

```ruby

```

### looping constructs
- 

```ruby

```

### looping with iterators & blocks
- 

```ruby

```

### controlling loop flow
- 

```ruby

```

### handling exceptions
- 

```ruby

```

### raising exceptions
- 

```ruby

```

### exceptions: ensure & else clauses
- 

```ruby

```

### exceptions: retrying & rescue modifier
- 

```ruby

```

### throw & catch
- 

```ruby

```

### scope
- 

```ruby

```


---
## 4. STANDARD TYPES
### booleans
- 

```ruby

```

### numbers
- 

```ruby

```

### strings
- 

```ruby

```

### string operators & methods
- 

```ruby

```

### regular expressions
- 

```ruby

```

### symbols
- 

```ruby

```

### arrays
- 

```ruby

```

### enumerable
- 

```ruby

```

### hashes
- 

```ruby

```

### ranges
- 

```ruby

```

### parallel assignment
- 

```ruby

```


---
## 5. METHODS IN DEPTH
### default parameter values
- 

```ruby

```

### variable length parameter lists
- 

```ruby

```

### keyword arguments
- 

```ruby

```

### method aliasing
- 

```ruby

```

### operators
- 

```ruby

```

### method calls as messages
- 

```ruby

```

### method_missing
- 

```ruby

```


---
## 6. MORE RUBY TOOLS (BLOCKS, CONSTANTS, MODULES)
### blocks
- 

```ruby

```

### block local variables
- 

```ruby

```

### using blocks
- 

```ruby

```

### from block to proc
- 

```ruby

```

### lambdas
- 

```ruby

```

### using procs & lambdas
- 

```ruby

```

### constants
- 

```ruby

```

### modules
- 

```ruby

```


---
## 7. PUTTING RUBY TO WORK
### organizing source code
- 

```ruby

```

### gems & managing dependencies
- 

```ruby

```

### testing frameworks
- 

```ruby

```

### debugging tools
- 

```ruby

```

### packaging & distributing code
- 

```ruby

```

### resources
- 

```ruby

```
