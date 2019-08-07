## Fitting: what are the parameters in your model that best describe the data 

To figure out the inner workings of (physical) phenomena, data is collected to examine any dependencies. That could be the mass of the Higgs boson, the decay of uranium, but also the number of children in a family as function of the average length of the parents, or the time of travel between home and university as function of the time of day. Each measurement is accompanied by an uncertainty that indicates the precision by which the magnitude is measured. As we've seen before: the smaller the error, the more accurate the measurement and the more 'important' it is in regards to comparing the measurements to your model. Once you've found a good description of the collected data, you can use your model to do predictions in areas that you have not yet measured and at the same time work towards an interpretation to the cause of that correlation.

In this part of the module we'll study in detail the result of the earlier mentioned fictional research: the lengths of women as function of the income of their parents. Is there, or isn't there a relationship to be observed in the data? To study this, first we have to determine the parameters and the uncertainty of the hypotheses (there is/isn't a relationship). It's most insightful to use an example when discussing the best way of determining the values of your parameters (and the uncertainty of them). After the example (the boiling point of alcohol) we'll apply our newfound knowledge in a more concrete assignment related to our case.

### [Example]: Determining the boiling point of alcohol during a practical

During a practical groups of students were assigned the task to determine the boiling point of alcohol. Because of a lack of time each group only had time for 1 measurement. There were six thermometers in the room that could measure teh temperature to 1 degree Celsius accurate and four thermometers that could do measurements to 0.5 degrees accurate. The list with measurements done by the ten groups of students is as follows and the graph with values is shown at the bottom of this example.

group number students (x)                   |  1   |  2   |  3   |  4   |  5   |  6   |  7   |  8   |  9   | 10 
measured boiling point in $$^\circ$$C (y)  | 78.2 | 80.2 | 78.7 | 78.9 | 77.5 | 79.7 | 78.1 | 79.0 | 79.6 | 78.4 
uncertainty ($$\sigma$$, error on y)       |  1   |  1   |  1   |  0.5 |  1   |  1   |  0.5 |  0.5 |  1   | 0.5


#### [example step 1]: creating a model and the goal of the exercise

The boiling point of alcohol is a natural constant and does not depend on the group of students that perform the measurements. In this case the 'model' we have is a flat line and we're actually trying to determine the boiling point of alcohol that best complies with the measurements. It is clear that 78$$^\circ$$ is a better estimation than 70$$^\circ$$ and 79$$^\circ$$ is better than 81$$^\circ$$, but what exactly is the 'best' value? In short: what is the average of the whole class?

#### [example step 2]: a measurement for 'how good' the model describes the data: the $$\chi^2$$ measure 

To find the 'best' value we need a measure (metric) that describes the 'quality' of the fit. Here we use the  $$\chi^2$$-measure: the sum of the average deviation of the measurements and the model weighed by their error. For each point we determine the distance of the measurement (expressed as the error of measurement at that point) to the value that the model predicts for that point. The sum of those deviations for each measurement is called the $$\chi^2$$.

More formal:
$$\chi^2(\vec{\alpha}) = \sum_{i~ {\rm (datapoints)}}  \left(\frac{  y_i - f(x_i|\vec{\alpha}) }{\sigma_i}\right)^2$$

Here $$\vec{\alpha}$$ is the vector with parameter that are used in your model. For each choice of parameters in your model the distance of each measurement to the model changes and gives a new $$\chi^2$$.

This expression seems more complicated than it actually is:

   1. the $$\chi^2$$ is just a number

   2. in our model there is only 1 free parameter, the boiling point of alcohol $$T_0$$ to be precise.
      Our model reduces to: $$f(x) = T_0$$ and the vector $$\vec{\alpha}$$ is reduced to 1 parameter, the constant $$T_0$$.
	  
#### [example step 3]: finding the best value of the model parameters

In the fitting procedure we look for the value of parameters in your model that result in the smallest $$\chi^2$$, because with those values for the parameters the measurements will lie, on average, closest to the model. Using a computer we'll try different values for $$T_0$$ and calculate the $$\chi^2$$ for each.

If, for example, we test the hypotheses $$T_0=78.0$$ the following $$\chi^2$$ is associated:
$$
\begin{eqnarray}
   \chi^2(T_0=78.0)&=&    
   \tiny{
   \left( \frac{(78.2-78.0)}{1.0} \right)^2+
   \left( \frac{(80.2-78.0)}{1.0} \right)^2+
   \left( \frac{(78.7-78.0)}{1.0} \right)^2+
   \left( \frac{(78.9-78.0)}{0.5} \right)^2+
   \left( \frac{(77.5-78.0)}{1.0} \right)^2}\\
   &~& 
   \tiny{
  +\left( \frac{(79.7-78.0)}{1.0} \right)^2+
   \left( \frac{(78.1-78.0)}{0.5} \right)^2+
   \left( \frac{(79.0-78.0)}{0.5} \right)^2+
   \left( \frac{(79.6-78.0)}{1.0} \right)^2+
   \left( \frac{(78.4-78.0)}{0.5} \right)^2
   }\\
   &=&19.0
\end{eqnarray}
$$

You can try different values of $$T_0$$ and calculate the $$\chi^2$$ for each. The distribution is drawn in the plot on the right hand side below. A clear minimum can be seen and the value of $$T_0$$ for which the $$\chi^2$$ is at a minimum is called $$T_0^{\rm best}=78.2$$.

#### [example step 4]: the uncertainty of parameters in your model

Each value of your parameters that is different from $$T_0^{\rm best}$$ will change the value of the $$\chi^2$$ (it gets larger which means a worse match with the data). The difference between the values of the $$T_0$$ for which the $$\chi^2$$ increases exactly 1 unit and $$T_0^{\rm best}$$ is called the uncertainty on $$T_0$$. This is often described as $$\Delta T_0$$. When calculating the $$\chi^2$$ we see that there is an area $$ 78.5 < T_0 <78.9$$ where the $$\chi^2$$ differs less than 1 unit from $$\chi^2_{min}$$. The result of the fit, and with that the result of the combined estimation of the boiling point of alcohol by the entire group of students is given by:

   Boiling point alcohol = $$78.2 \pm 0.2 ^\circ C$$

**Note:** Although we assume that the error in $$T_0$$ is symmetrical, this is not always the case. You have to always evaluate the negative and positive error separately, by monitoring how the $$\chi^2$$ changes if you increase or decrease the parameters.

#### [example step 5]: the corresponding graphs

![](FitExampleWebsite.png){: style="width:90%"}

The example that we've walked through is the so-called 'fitting' of a simple model with 1 parameter to the collected data. Even when we have a more complicated model, for example the polynomial of the first degree $$f(x)=ax+b$$, we find the best values of the two parameters by varying $$a$$ and $$b$$ and determining for which values the $$\chi^2$$ is minimal.

## Assignment 3: average length of women in Denmark

Let's refocus on the case from before. So in Denmark there is a group researchers studying whether the length of women is dependant on the income of their parents. They've chosen 10 categories of income and although they've tried to find as many equal numbers of women from each category for their study, the number of women with parents within the extremes of the income categories (very poor and very rich) is limited. This is clear by the greater error on the estimation of the average length within those groups.

Category (x)        |  1 (very poor)   |  2    |  3    |  4    |  5    |  6    |  7    |  8    |  9    | 10 (very rich)
Avg. length (y)      | 171.1 | 169.1 | 170.8 | 169.4 | 173.0 | 171.0 | 174.0 | 174.0 | 173.0 | 176.0 
Error ($$\Delta y$$)  |  4    |  4    |  2    |  2    |  2    |  2    |  2    |  2    |  4    |  4

Write a program `statistics_3.py` in which you find the average of the length of women in Denmark by fitting the data given above to the function $$f(x) = C$$. That means for this assignment you will assume there is no correlation between the income of the parents and the length of their daughters. Implement the steps you've practiced in the example about measuring the boiling point of alcohol.

Make sure the program displays the data (with errors) on the screen and also gives the best values of the fit you have found. Just lik in the left hand plot in the example above. To plot the data in Python use the function `plt.errorbar(x, y, yerr=yerror)`. Research the internet about how to use this function.

`Print` the result, accurate with 1 decimal, in the following way:
{: .language-python}
    The fit (flat line) provides an average length of xxx.x cm
