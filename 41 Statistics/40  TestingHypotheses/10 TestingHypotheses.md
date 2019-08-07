
## Assignment 5: Testing hypotheses

A part of the researchers think the data suggests that there is a linear relationship within the data, as opposed to another part of the researchers who think there is no dependancy and that observed light dependancies are just a coincedence caused by the specific samples that were collected. We'll conclude this module by supplying quantitative data to this ongoing discussion.

The question really is: "how rare is the case that, given that there is <b>no</b> actual relationship, a series of samples (of this size in each category) produces a value for the slope that is of equal value as it is in the data or even larger?". This fractions is often encountered in literature and is also known as the <font color = 'red'> p-value </font>.

#### Assignment 5: Simulate random data-sets and calculate teh p-value

Write a program `statistics_5.py` that answers the aforementioned question by examining how rare it is that the observed slope is present within the data, when in actuality there is no dependancy at all.

To answer this question, apply the following strategy:

   1. Simulate a data-set:

      * Work by the assumption of a 'flat' hypothesis: f(x) = C, where C has the same value as in assignment 3.

      * Choose from each of the 10 income categories a 'random' measurement by using the `np.random.normal(average, spread)` function, where the average in each category is given by the value that you found in assignment 3. For the spread in each category you should use the uncertainty of the average length in that specific category from the original data-set. For example, an uncertainty of 4 cm in the income category 1.
	
      * Assign the same error as in the original data to the uncertainty of the random chosen average length in each category. For example, 2 cm in income category 5.
	   
   2. Fit a function of the form f(x) = ax+b and determine the slope (a).

   3. Repeat the above mentioned a large number of times (10000 times for example) and remember for each of the data-sets what the slope was. Keep track of what fraction of the simulated datasets (coincedentally) had a slope equal (or greater than) that of the original dataset (see assignment 4).

   4. Create a graph (histogram, see below) of all slopes and clearly display the values you've found in the data and the corresponding p-value.
	  
      ![](ExamplePvalue.png){: style="width:60%"}

   5. `Print` the p-value to the screen at the end of the program: in percentages, 2 decmial accurate.
    
      {: .language-python}
         The p-value for the alternative hypothesis: x.xx percent


In general we follow the rule that when the p-value is smaller than 5% we speak of a 'coincidence'. If the p-value is larger than 5% then we conclude that the observed trend is not described by the flat hypothesis and that we've found evidence for a relation.

*Note:* A relationship that you've found does not have to mean it is a causal relationship. Imagine that a relation is found (and always keep in mind that the observed effect can still be coincedental), what could the underlying cause possibly be? Richer people: eat healthier, live in houses in neighbourhoods with better air quality, or the reverse that in our society the length might cause a higher income? Etc etc. Dig dig dig until you've dug to the core and find something new that no one has ever seen. That is science!


