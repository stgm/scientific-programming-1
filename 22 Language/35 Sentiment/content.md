# Sentiment analysis

Bepaal sentiment van een lange tekst gegeven twee woordenlijsten.

	def load_words(filename):
	  	content = open(filename)
	    lines = content.readlines()
	    content.close()
	    return lines

	def load_good_words():
		return load_words("good_words.txt")

	def load_bad_words():
		return load_words("bad_words.txt")

	def sentiment_of_word(word):
		if word in good_words:
	    	return 1
	    elif word in bad_words:
	    	return -1
	    else
	    	return 0

	def sentiment_of_text(text):
		score = 0
	    for word in words_from(text):
			sentiment = sentiment_of_word(word)
	        score += sentiment
	    return score

	total_score = sentiment_of_text("...")
	if total_score > 0:
		print("The text is mostly nice!")
	elif total_score < 0:
		print("The text talks about mad or bad stuff :(")
	else:
	  	print("The text is not opiniated or just messy.")
