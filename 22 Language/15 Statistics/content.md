# 1. Text statistics

> Requirements:
>
> * calculate and filter loop strategies (from last module)
> * letter `in` string pattern
> * string comparison
> * a few string methods: `isalpha()`

One way to make sense of written texts is to calculate statistics about the form of the text. We do not look at what the text *means*, but examine its superficial properties. Say we define the following variable:


	source_text = "ASDF is the sequence of letters that appear on the first four keys on the home row of a QWERTY or QWERTZ keyboard. They are often used as a sample or test case or as random, meaningless nonsense. It is also a common learning tool for keyboard classes, since all four keys are located on Home row." # from the wikipedia

We could define a function `number_of_letters_in(text)` that calculates how many letters are actually in that string of text.

	def number_of_letters_in(text):
	    return len(text)

	print(number_of_letters_in(source_text))

This function actually only calls *another* function to perform the actual counting. Seen that way, we just defined the same function, but with a different name. That seems quite useless! So why might we define it? Let's check out what it does first.

In this case, the function doesn't quite do what it says it does. It promises to return the number of *letters* in a string. But if we run it, we see that it returns the number 296, which is the full *length* of the string, including spaces and periods. Usually we don't think of spaces and periods as *letters*, right?

So we need to filter those out to get a real answer, given that the name of the function promises as much!

> **Task**: rewrite the function `number_of_letters_in(text)` to count the number of letters in the string, as opposed to counting each individual character in the string.
>
> To do this, you'll need to build a loop that examines each individual *character* of the string, then decide if that character is actually a *letter*, and if so, count it. When done examining, the final count should be `return`ed.
>
> Hint: build the structure of your program using the **filter with loops** and **calculation with loops** strategies.

Solution:

	def number_of_letters_in(text):
	    count = 0
	    for letter in text:
	        if letter.isalpha():
	            count += 1
	    return count

	print(number_of_letters_in(text))

You can test your code using checkpy:

	checkpy text_statistics.py

## Splitting up texts

Texts can usually be split up into words and sentences. To later be able to analyze a text word-by-word or sentence-by-sentence, we might need to split things up. For example, if we can split up a text into words, we might calculate the number of words in the text.

> **Task**: write a function `number_of_words_in(text)` which takes a string containing text, and returns a list containing each individual word from that text.
>
> Your strategy might look like this:
>
> 1. split up the original text using the `split()` method
> 2. calculate the length of the result from step 1
> 3. `return` the length from step 2
>
> So in summary, you take the result of one method, put it into another, then return.

Solution:

	def number_of_words_in(text):
		return len(text.split(" "))

> **Task**: write a function `number_of_sentences_in(text)` which takes a string containing text, and returns a list containing each individual sentence from that text. You can use the same strategy as above, but change the call to `split()`. How should it be different?

Solution:

	def number_of_sentences_in(text):
	    return len(text.split("."))

If you use the same strategy as above, you might encounter a problem. Test your code with the sample text and check the results by hand!

	print(number_of_words_in(source_text))
	print(number_of_sentences_in(source_text))

Most likely, you now see that the program counts 4 sentences, while you count only 3. There are 3 periods, so there are 3 well-formed sentences. How might we solve this problem? Try it!

Test your code using checkpy again:

	checkpy text_statistics.py

## Part 3

> ideeën:
>
> * average word length
> * number of words with letter "n" in them

