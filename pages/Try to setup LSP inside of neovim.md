- #Neovim
- Tutorials that did not work out
	- Working with this [tutorial](https://alpha2phi.medium.com/neovim-for-beginners-lsp-part-1-b3a17ddbe611)
	  collapsed:: true
		- We have the following goals, according to the tutorial above:
			- Configure the *nvim-lspconfig* plugin. This is the plugin that provides common configuration for various language servers.
			- Configure a language server installer to make it easy to install any language server.
			- Configure key mappings for the LSP features
			- Configure the *vim.lsp.omnifunc* function (:h *vim.lsp.omnifunc*) as the *omnifunc* (:h *omnifunc*) handler. The *omnifunc* option specified a function to be used for insert mode *omni* completion with `CTRL-x CTRL-O`. {{embed ((Do not currently understand this.))}}
			  id:: 63657b05-e1f2-4162-800a-566674a598f3
			- Configure the *vim.lsp.formatexpr* function as the handler for *formatexpr(:h formatexpr)*. The *formatexpr* option specifies an expression that is evaluated to format a range of lines for the *gqoperator* or automatic formatting *(:h formatoptions)*. {{embed ((Do not currently understand this.))}}
			- Configure LSP completion using coq.nvim and nvim-cmp. Previously, we talked about these two completion plugins in this article. #card
		- This tutorial did not work for me because it has a pre-requisite plugin that I did not completely understand and would take too long to learn.
-