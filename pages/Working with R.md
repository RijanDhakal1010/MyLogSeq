- Installation
	- [How to install R for VScode according to microsoft](https://code.visualstudio.com/docs/languages/r)
		- ```
		  install.packages("languageserver")
		  ```
			- On Arch based systems, use `sudo pacman -S tk`.
		- To use a REPL inside VScode
			- make sure jupyter is installed
				- `pip3 install jupyter`
			- make sure `IRkernel` is installed
				- `install.packages('IRkernel`)`
				- `IRkernel::installspec()`
			- [How to set R for use inside Jupyter](https://stackoverflow.com/questions/56497422/using-jupyter-r-kernel-with-visual-studio-code)
			- Make sure `Jupyter` is installed **DUH**
			- On Arch
				- `yay -S code-features`
- Installing R packages:
	-