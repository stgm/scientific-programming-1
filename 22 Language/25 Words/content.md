# Word use

Implement a program that lists all the words from a given text string. Each word in the output should be unique, written in lowercase, and no remnants of punctuation marks or white space should be left in the words as printed.


## Background

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

## Specification

Implement the TODOs above.

1. Implement `cleaned_up(word)` as directed in the TODO. Use Python string methods to do the cleanup.
2. Add cleaning to the existing `all_words_from(text)` function. Use the **transform** loop strategy.

## Unique words

If we would like to know which words from the dictionary are used in a particular text, we do not need to know how often each word appears. So if we list the words from the text, it is not necessary to list words multiple times.

> Task: write a method `unique_words_from(text)` that returns, as a list, each unique word that is used in the text. Don't forget to take each word's `cleaned_up` version! 

	def unique_words_from(text):
		# TODO


## Hints

* string methods [Built-in Types — Python 3.7.4 documentation](https://docs.python.org/3/library/stdtypes.html#text-sequence-type-str)


## Testing

Don't forget to check your code using:

	checkpy content_analysis.py

- empty input
- 1-word input
- multiple-word input
- words with punctuation
- words with double blanks / empty words  "word<space><space>huh"



## Solution

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
