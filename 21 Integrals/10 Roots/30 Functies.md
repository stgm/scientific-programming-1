# Roots

Write a program that calculates the roots of the polynomial $$f(x)=x^2+2x-10$$.

    # python roots.py
    The roots are -4.32 and 2.32

![](PolynoomAnalyse.png)


## Specification

* Call your program `roots.py`.

* Create one function `roots(a, b, c)` that has the task to calculate the roots of the polynomial $$f(x)=ax^2+bx+c$$.

* There are two possible results the function could `return`:

    * an empty list `[]` when there are no roots
    * a list of two elements `[n1, n2]` in which `n1` and `n2` are the roots of the polynomial

* In any case you should plot the function and display the roots clearly in the graph that you calculated.

## Hints

* Calculate the roots with use of the *quadratic*-formula.

* To make sure you can print the result clearly, call the function like we do in our example, and store the result:

        result = roots(1, 2, -10)

* Later on also test your program with a polynomial that has no roots (check if the list is empty). The program should print that the roots do not exist:

        This function does not have roots.

## Testing

If you use `checkpy`, note that it does not check if you program has the correct output. Instead it checks if the function `roots()` `return`s the correct result.

    checkpy roots.py

(Does it not work? Update once again with the command `checkpy -u`.)
