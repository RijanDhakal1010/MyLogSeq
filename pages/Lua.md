- [Learn X in Y](https://learnxinyminutes.com/docs/lua/)
- # Outline
- Variables and flow control
	- Fairly simple.
	- Covers
		- Variables
		- Conditional statements
		- Ranges
		- Bools
		- Flows (`for loops`)
			- {{embed ((63ed0fa9-deba-4fc2-a1fb-ba5c51881848))}}
			-
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
- ### Lua allows anonymous functions
- ```lua
  function adder(x)
    -- The returned function is created when adder is
    -- called, and remembers the value of x:
    return function (y) return x + y end
  end
  ```
- In the above example, when `a1=adder(9)` is defined and if `a1(16)` then `x=9` from the argument supplied to `adder` and `y=16` from the argument supplied to `a1()`. The final value becomes 25.
- ## Tables in lua
- Tables are the only compound data structure in Lua. They are associative arrays. They are hash-lookup dicts that can also be used as lists.
- Dict literals have string keys by default
	- t = {key1 = 'value1', key2= `false`}
	  id:: 63ed07be-2d85-4bb3-a8f7-a2ab1c896289
- On the above table `t`:
	- String keys can use dot notation
		- `print(t.key1)` will print `value1`
	- To add a new key
		- `t.newkey = {}`
	- To remove an old key set it to `nil`
	  id:: 63ed08d2-fef6-4a4c-b474-3644ae2b8a74
		- `t.key2 = nil`
- For a table like `u = {['@!#'] = 'qbert', [{}] = 1729, [6.28] = 'tau'}`, if you do `a = u[''@!#]`, now `a` is `qbert` but if you do `b = u[{}]`, the value comes out to be nil. This is because keys are matched using numbers and strings but fails for `table objects` (of table objects are used for keys). So it is better to use strings and numbers for keys.
- Iterations through tables
	- id:: 63ed0fa9-deba-4fc2-a1fb-ba5c51881848
	  ```
	  for key, val in pairs(u) do  -- Table iteration.
	    print(key, val)
	  end
	  ```
- # Miscellaneous questions
- TODO What is camel case?
- TODO What is a double?
- TODO What does it mean for a function to be first class?
- TODO What is a parens in lua?
-