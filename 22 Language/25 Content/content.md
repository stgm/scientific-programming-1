# Content analysis

Requirements:

* **transform** loop strategy **(new!!)**
* string methods [Built-in Types — Python 3.7.4 documentation](https://docs.python.org/3/library/stdtypes.html#text-sequence-type-str)

Let's go from simply *counting* letters and words towards looking at each part of a text. For example, here is some code that prints each word from the text on a separate line:

	def all_words_from(text):
	    split_words = text.split(" ")
	    return split_words

	def print_words(words):
	  	for word in words:
	      	print(word)

	print_words(all_words_from(source_text))

Try out the code! You'll notice that the words aren't quite as "clean" as one might expect. A few words contain periods (.) and some contain capital letters while others don't. To do more interesting processing, we will need to clean it up. Here's a starting point for the same program which output "cleaned up" words:

	def cleaned_up(word):
	    # TODO take word, remove unwanted stuff, make lowercase, return

	def all_words_from(text):
	    split_words = text.split(" ")
	    # TODO call cleaned_up for each word
	    return cleaned_up_words

	def print_words(words):
	  	for word in words:
	      	print(word)

	print_words(all_words_from(source_text))

There are two `TODO`s above:

1. Implement `cleaned_up(word)` as directed in the TODO. Use Python string methods to do the cleanup.
2. Add cleaning to the existing `all_words_from(text)` function. Use the **transform** loop strategy.

> Don't forget to check your code using:
> 
>     checkpy content_analysis.py

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

## Unique words

If we would like to know which words from the dictionary are used in a particular text, we do not need to know how often each word appears. So if we list the words from the text, it is not necessary to list words multiple times.

> Task: write a method `unique_words_from(text)` that returns, as a list, each unique word that is used in the text. Don't forget to take each word's `cleaned_up` version! 

	def unique_words_from(text):
		# TODO

Solution:

	def unique_words_from(text):
	  	result = []
	    for word in all_words_from(text):
	      	if word not in result:
	          	result.append(word)
		return result
  
	# return set(words_from(text)) # trick that we're NOT going to use

	def unique_words_of_length_from(text, length):
		n = 0
	    for word in unique_words_from(text):
			if len(word) == length:
	          	n += 1
	    return n

	# tot slot: number_of_words_in(text) kan nu aangepast om unique_words_from te gebruiken!
