- Goal: To make a custom `hugo` shortcode that can redact text with the option to interactively remove the redaction by clicking. I want the ability to black out text in such a way that the text becomes visisble when clicked by the user.
- I am using this [guide](https://gohugo.io/templates/shortcode-templates/) on the official hugo website to try and make my short code using this [stackoverflow.com post](https://stackoverflow.com/questions/28615544/how-to-create-spoiler-text) that shows how to implement the feature I want using html/css.
	- ```
	  .spoiler{
	    background-color: gray;
	    color: transparent;
	    user-select: none;
	  }
	  
	  .spoiler:hover{
	    background-color: inherit;
	    color: inherit;
	  }
	  
	  <h3>In the movie, <span class="spoiler">the hero kills his wife.</span></h3>
	  ```
- The folder that the files sits inside of is `~/<hugo_folder>/layouts/shortcodes`
-