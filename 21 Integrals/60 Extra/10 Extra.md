# Fractals - Mandelbrot set

You probably already know those beautiful multicoloured pictures in which patterns repeat themselves untill they are infinitely small. These incredibly complex patterns, called *fractals*, funnily enough are product of a small set of simple (mathematical) rules. Often times in nature do we find such simple hidden mechanisms for complex fenomena, however hard they are to find out about. In this assignment we delve a little deeper into the maths behind fractals and with that knowledge we'll try to recreate one of the most well-known fractals: the [Mandelbrot set](https://en.wikipedia.org/wiki/Mandelbrot_set).

<p align="center">
![](mandelbrot.png){: style="width:50%"}
</p>

The goal of this extra assignment is: write a program `fractal.py` that displays the Mandelbrot set on the screen.

### Mathematical intermezzo: complex numbers

To get a better understanding of the maths behind a fractal, we must first introduce a new mathematical concept: *complex numbers*.

Complex numbers maintain a special place in maths and can be found in many subject in mathematics as well as physics. During the lectures you'll get to see many more characteristics, but here we introduce the bare mininum.

   - defenition: we define $$ i = \sqrt{-1}$$
   
A complex number (z) is made up out of two components: a real and an imaginary part.

   - complex number: z = $$\alpha + \beta i$$

, with  $$\alpha$$  the real and  $$\beta i$$  the imaginary part.

A common way to imagine these numbers is the so called *complex field*, a 2-dimensional field with a real axis and an imaginary axis that represents the complex part of the number, as can be seen below. Two examples of complex nubmers are $$c = -5 + 3i$$ and $$c=-2-4i$$. These are both represented in blue. All numbers we usually use (0, -3, $$12/67$$, $$\pi$$, $$e$$, 10465, ...) are situated on the real axis. There are also a couple of complex numbers in red; we'll come back to those in time.

<p align="center">
![](ComplexeGetallen.png){: style="width:70%"}
</p>

Adding complex numbers is simply adding the real part and the complex part individually, but multiplying them takes some caution. You have to take into account that $$i^2 = -1$$. It's most apparent when exponentiating:

   * squaring: $$(\alpha + \beta i)^2 = (\alpha^2 - \beta^2) + (2 \alpha \beta)i$$

For example: $$(2+i)^2 = 3+4i$$. If you were to add the original number $$(2+i)$$ to it again the result would be $$5+5i$$. These numbers are all three denoted in red in the figure of the complex field above. These calculation are the ones we'll be performing in the assignment.

This is all of the mathematical background on complex numbers you'll be needing for this assignment. Now we can get to work.


### Functies van complexe getallen, reeksen en fractals 

Net als voor gewone getallen kunnen we ook functies definiëren voor complexe getallen. In deze opgave gaan we werken met polynomen van de volgende vorm:

   $$f(z) = z^2 + c$$ 

, waarbij zowel $$z$$ als $$c$$ een complex getal zijn. De enige vrijheid die we nog hebben is in de keuze van het getal $$c$$. De uitkomst van de functie is weer een complex getal.

**Reeksen:**

Door het getal dat de uitkomst van de operatie (functie) is weer opnieuw als argument in de functie in te vullen krijgen we een reeks getallen.

   - stap 1: kies een complex getal $$z_0$$
   
   - stap 2: bereken $$f(z_0) = z_0^2 + c$$. Dit getal noemen we $$z_1$$.   

   - stap 3: bereken $$f(z_1) = z_1^2 + c$$. Dit getal noemen we $$z_2$$.   

   - stap 4: ...

Meer algemeen noteren we dit $$n$$ keer uitvoeren van de functie als volgt: $$z_n = f^{(n)}(z_0)$$. Voor elk startpunt in het complexe vlak kunnen we nu kijken hoe de reeks zich ontwikkelt. 

**Fractals (algemeen):**

Voor elke keuze van een functie $$f(z)$$ kunnen we nu de punten in het complexe vlak verdelen in twee groepen. Meer specifiek; voor een specifiek (start)punt $$z_0$$ geldt:

   - de reeks convergeert:  $$\rightarrow$$  $$z_0$$ is **wel** onderdeel van de set

   - de reeks divergeert: $$\rightarrow$$ $$z_0$$ is **geen** onderdeel van de set

Door vervolgens een kleurcode toe te kennen aan de snelheid waarmee een specifiek startpunt in het complexe vlak divergeert dan wel convergeert krijgt elk punt in het complexe vlak een kleur. Door dit te plotten ontstaan de beroemde fractals. 


**De Mandelbrot set:**

De Mandelbrot set is gedefiniëerd door de functie die we al eerder gezien hebben met een speciale keuze voor de constante $$c$$, namelijk het startpunt zelf is. Met $$c = z_0$$ krijgen we dan: 
    
   Mandelbrot: $$f(z) = z^2 + z_0$$ 
    
, waarbij $$z_0$$ het startpunt is. 

Voor een gegeven startpunt kan de reeks divergeren of convergeren. Als voorbeeld van beide gevallen staan hieronder de eerste 10 punten in de reeks voor twee startpunten $$z$$ (= $$z_0$$) = $$-0.20 + 0.25i$$ en $$z$$ (= $$z_0$$) = $$0.50 + 0.25i$$.

      z0 = -0.20 + 0.25i       z0 = 0.50 + 0.25i
      ------------------       ------------------

    z0 = -0.200 + 0.250 i      z0 =  0.50 +  0.25i
    z1 = -0.223 + 0.150 i      z1 =  0.688 + 0.500 i
    z2 = -0.173 + 0.183 i      z2 =  0.723 + 0.938 i
    z3 = -0.204 + 0.187 i      z3 =  0.143 + 1.605 i
    z4 = -0.193 + 0.174 i      z4 = -2.055 + 0.710 i
    z5 = -0.193 + 0.183 i      z5 =  4.221 + -2.669 i
    z6 = -0.196 + 0.180 i      z6 = 11.190 + -22.279 i
    z7 = -0.194 + 0.180 i      z7 = -370.655 + -498.339 i
    z8 = -0.195 + 0.180 i      z8 = -110956.038 + 369424.274 i
    z9 = -0.195 + 0.180 i      z9 = -124163052007.623 + -81979707256.034 i

Nu is het tijd om zelf een fractal te tekenen. 

### Opdracht: 

Bepaal in je programma `fractal.py` voor elk punt $$z_0$$ in het complexe vlak of de reeks convergeert of divergeert onder de polynoom voor de Mandelbrot set:

   $$f(z) = z^2 + z_0$$. 
    
Als de reeks convergeert teken je het punt blauw, als het divergeert teken je het wit.

Hoewel je in deze opdracht zelf zult moeten bepalen welke definitie je gaat hanteren om te bepalen of een reeks wel of niet convergeert zullen we de snelheid waarmee dat gebeurt in deze opgave verder negeren. Onze plot zal daarmee maar uit twee kleuren bestaan. Iets saaier dan de officiële plot natuurlijk, maar genoeg voor deze opdracht.

**Specificaties voor de scan (plot):**

De resolutie van de grafiek moet de volgende dimensies hebben:

    - reële as:      500 punten tussen -2.00 en 1.00 

    - imaginaire as: 500 punten tussen -1.50 en 1.50 


Als je klaar bent met de opgave en toch meer kleur toe wilt voegen door alsnog de diverentiesnelheid mee te nemen dan houden we je niet tegen natuurlijk.

## Checkpy

Er is voor deze opdracht geen checkpy oplossing aanwezig. You're on your own.
