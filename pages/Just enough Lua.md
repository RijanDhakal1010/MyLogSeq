- [What are pcalls](https://www.lua.org/pil/8.4.html)
  collapsed:: true
	- "All Lua activities start from a call by the application, usually asking Lua to run a chunk. If there is any error, this call returns an error code and the application can take appropriate actions. In the case of the stand-alone interpreter, its main loop just prints the error message and continues showing the prompt and running the commands."
	  id:: 6367d772-4ab8-46e0-b15e-459e2d0bc685
	- "If you need to handle errors in Lua, you should use the  `pcall`  function (*protected call*) to encapsulate your code."
		- [[Nov 6th, 2022]]
		  collapsed:: true
			- ((6367d772-4ab8-46e0-b15e-459e2d0bc685))
				-
		- What this really means is that if we want to handle something manually we should use `pcalls`.
		- How does this work?
		  collapsed:: true
			- You have a piece of Lua code and want to catch any error raised while running that code.
			- ```Lua
			  function foo ()
			          ...
			        if unexpected_condition then error() end
			          ...
			        print(a[i])    -- potential error: `a' may not be a table
			          ...
			  end
			  ```
			- If you want to make a protected call to the above function you would use the following code setup
			- ```lua
			  if pcall(foo) then
			        -- no errors while running `foo'
			        ...
			  else
			        -- `foo' raised an error: take appropriate actions
			        ...
			  end
			  ```
			- The most important takeaway from `pcalls` is that the function is being called in a protected manner where it catches any errors while the function is running. If the function runs its course without any errors, `pcall` returns *true* and the output of the function. Otherwise the output is *false*.
-
- [[Comments]]
  collapsed:: true
	- [[Nov 6th, 2022]]
	  collapsed:: true
		- ((6367d772-4ab8-46e0-b15e-459e2d0bc685))
			- This seems to explain the `require` syntax of lua