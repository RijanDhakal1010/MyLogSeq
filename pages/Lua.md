- [Learn X in Y](https://learnxinyminutes.com/docs/lua/)
- # Outline
- Variables and flow control
	- Fairly simple.
	- Covers
	  collapsed:: true
		- Variables
		- Conditional statements
		- Ranges
		- Bools
- Functions
	- Covers the Fibonacci sequences in an example with recursion
-
- ## Tables in Lua
- Tables are the only compound data feature Lua has.
	- They are similar to php arrays or js objects, they are hash-lookup dicts that can also be used as lists.
	- In tables, dict literals have string keys by default.
		- t = {key1='value', key2='false'}
			- `print(t.key1)` -- this will print 'value'
			- `t.newKey = {}`  -- Adds a new key/value pair.
			- `t.key2 = nil`   -- Removes key2 from the table.
- ## Modules in Lua
- ## Functions in Lua
- ```lua
  function adder(x)
    -- The returned function is created when adder is
    -- called, and remembers the value of x:
    return function (y) return x + y end
  end
  ```
- In the above example, when `a1=adder(9)` is defined and if `a1(16)` then `x=9` from the argument supplied to `adder` and `y=16` from the argument supplied to `a1()`. The final value becomes 25.
- # Miscellaneous questions
- What is camel case?
- What is a double?
-