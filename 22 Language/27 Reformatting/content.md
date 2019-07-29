## Deconstructing and reconstructing

If you know how to split as well as how to join strings again, you might implement a function that *reformats* text. In this case, we need a formatter that ensures a text has a maximum number of characters per line. In the sample text above, there are three sentences, but they are all on the same line of code. Depending on your code editor, the text might be cut off at the right, or newlines have been inserted at some places to make sure you can read it all. Either way, it doesn't really look *nice*: the newlines have been inserted in the middle of words. We can do better!

> Task: write a function `text_to_lines(text, max_length)` which neatly formats the given text into lines of length `max_length`. Words should not be cut off, but moved to the next line when necessary.
>
> Strategy:
>
> * split up the text into individual **words**
> * create a variable to hold the newly made string
> * consider each word to see if a newline has to be inserted **before** it
> * add the newline if needed, and then the word
> * when finished with all words, re-join the string and return it
>
> Note that this looks quite a bit like the filter + calculation loop strategy you used above!

Meh solution:

	# TODO spatie bug
	def text_to_lines(text, max_length):
	    lines = [""]
	    split_text = text.split(" ")

	    for word in split_text:
	        if len(lines[-1]) + len(word) <= max_length:
	            lines[-1] += " " + word
	        else:
	            lines.append(word)
	    return "\n".join(lines)

	print(text_to_lines(text, 40))

	def number_of_lines_in(text):
	    return len(text.split("\n"))

	print(number_of_lines_in(text_to_lines(text)))
