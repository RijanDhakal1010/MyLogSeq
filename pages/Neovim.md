- The way to install fonts was to use `yay nerd-fonts-go-mono `
- # Making a config from scratch
- The first line in the `init.lua` file can be `require("plugins).setup()`
  collapsed:: true
	- since lua reads `lua/plugins` as `lua/`, we can use `require("plugins")`.
	- #unsure what does `.setup()` do?
- How to bootstrap `packer.nvim`?
	- According to the author of `packer.nvim` we can use the following code to bootstrap packer
	- ```lua
	  local ensure_packer = function()
	    local fn = vim.fn
	    local install_path = fn.stdpath('data')..'/site/pack/packer/start/packer.nvim'
	    if fn.empty(fn.glob(install_path)) > 0 then
	      fn.system({'git', 'clone', '--depth', '1', 'https://github.com/wbthomason/packer.nvim', install_path})
	      vim.cmd [[packadd packer.nvim]]
	      return true
	    end
	    return false
	  end
	  
	  local packer_bootstrap = ensure_packer()
	  
	  return require('packer').startup(function(use)
	    use 'wbthomason/packer.nvim'
	    -- My plugins here
	    -- use 'foo1/bar1.nvim'
	    -- use 'foo2/bar2.nvim'
	  
	    -- Automatically set up your configuration after cloning packer.nvim
	    -- Put this at the end after all plugins
	    if packer_bootstrap then
	      require('packer').sync()
	    end
	  end)
	  ```
	- The above code works
-