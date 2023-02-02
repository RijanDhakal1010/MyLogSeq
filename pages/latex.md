- How to increase the indent?
  collapsed:: true
	- Of the way to do this is to use  `\usepackage{setspace}` and configuration `\doublespacing`
	- Other configurations are
		- `\doublespacing`
		- `\onehalfspacing`
	- In order to make a part of the text of your document singlespaced, you can put:
	- ```
	  \begin{singlespace}
	  ```
	- at the beginning of the text you want singlespaced, and
	- ```
	  \end{singlespace}
	  ```
- How to include external paragraphs?
	- Use the `\include{filename}` (no .tex extension)
	- Also, you can use the `\insert{filename}` (no .tex extension)
-