# Text statistics

Welcome.

# 1. Letters

> Requirements:
>
> * calculate and filter loop strategies (from last module)
> * letter `in` string pattern
> * string comparison
> * a few string methods: `isalpha()`

Write a function that calculates how many letters are in a given string.

    >>> print(number_of_letters_in("He counted more than 7 petals on each flower."))
    35

## Background

One way to make sense of written texts is to calculate statistics about the form of the text. We do not look at what the text *means*, but examine its superficial properties. Say we define the following variable:

	source_text = "ASDF is the sequence of letters that appear on the first four keys on the home row of a QWERTY or QWERTZ keyboard. They are often used as a sample or test case or as random, meaningless nonsense. It is also a common learning tool for keyboard classes, since all four keys are located on Home row." # from the wikipedia

One statistic we could calculate is the length of the text, using the built-in `len()` function from Python.

	>>> print(len(source_text))
    296

We can also define slightly more fine-grained statistics. For example, we might count only the *letters in a string*. Let's say a *letter* is any alphabetic character that occurs in a string. For our `source_text`, this is definitely less than 296, because it contains spaces as well as periods.

## Strategy

To do this, you'll need to build a loop that examines each individual *character* of the string, then decide if that character is actually a *letter*, and if so, count it. When done examining, the final count should be `return`ed.

Hint: build the structure of your program using the **filter with loops** and **calculation with loops** strategies.

Hint: checkout [link](https://docs.python.org/3.7/library/stdtypes.html#string-methods) for string methods.

## Testing

You can test your code using checkpy:

	checkpy text_statistics.py


# 2. Words

Write a function `number_of_words_in(text)` which takes a string containing text, and returns a list containing each individual word from that text.

## Background

Texts can usually be split up into words and sentences. To later be able to analyze a text word-by-word or sentence-by-sentence, we might need to split things up. For example, if we can split up a text into words, we might calculate the number of words in the text.

## Strategy

Your strategy might look like this:

1. split up the original text using the `split()` method
2. calculate the length of the result from step 1
3. `return` the length from step 2

So in summary, you take the result of one method, put it into another, then return.

## Testing

You can test your code using checkpy:

	checkpy text_statistics.py


# 3. Sentences

Write a function `number_of_sentences_in(text)` which takes a string containing text, and returns a list containing each individual sentence from that text.

    >>> print(number_of_sentences_in("She stopped. Turned around. Oops, a bear. Just like that"))
    4

## Strategy

You can use the same strategy as above, but split in a different way. How should it be different?

However, if you use the same strategy as above, you might encounter a problem. Test your code with the sample text and check the results by hand!

	print(number_of_words_in(source_text))
	print(number_of_sentences_in(source_text))

Most likely, you now see that the program counts 4 sentences, while you count only 3. There are 3 periods, so there are 3 well-formed sentences. How might we solve this problem? Try it!

## Testing

Test your code using checkpy again:

	checkpy text_statistics.py

# 4. Part 4

> ideeën:
>
> * average word length
> * number of words with letter "n" in them
