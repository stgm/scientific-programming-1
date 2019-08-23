# Style Guide

Programming code is preferably easy to read and understand. Note only for yourself, but also for collaborators. In this course it is important to not only take the functionality of the code into account ("how do I write code to do something") but also the quality of the code ("is my code readable"). Earlier, we already mentioned some guidelines on how to comment code. Below you can find more aspects on how to comment your code properly.

## Terminology

To start, some terminology:

- We often talk about "programs". A *program* is an entity, a piece of software designed to execute a task or an action. Think about a calculator on your phone, or Microsoft Word. Python itself is also a program. In this course, you write a variety of programs yourself. 
- We also often talk about "code". A piece of *code* is a fragment, often a part of a program. The word code is not countable (i.e. you cannot talk about "one code" or "two codes"). You can say "my code doesn't work", in that case it is evident that you talk about the code you just have been working on.
- A program consists of "lines" of code.

## Choice of Language

In this course, we work in English. Make sure you work in one language only: variable names and comments should both be in English. 

## Comments

It is just as easy to write a lot of comments in your code as writing too little comments. To determine where comments are really needed, we should put ourselves in the reader of the code. This could be someone else, someone that uses your code to write a nice program. But, it could also be yourself, a few months later, desparately trying to decipher your own code. What information does this reader need?

- Summaries of blocks of code. Often you have divided your code in functional blocks. Sometimes only a few lines of code. It is ususally not difficult to summarize and describe the functionality of that piece of code. 
- Warnings for potential problems. Maybe you came up with a temporal solution to a problem, of which you know it will not work for some cases (but for now its fine). In that case, it is handy to document your doubts with in a comment.
- Explanation of complex algorithms. Sometimes you write very complex code. In that case you can give an explanation of the algorithm or provide a link for more information.
- Source references. To avoid plagiarism, it is of course important to mention all sources used when fully or partially using other people's code. Even if you change this person's code it is important to still refer to the source.

### Example 1

Wanneer hoeft het nou bijvoorbeeld niet? Als je variabelenamen erg duidelijk zijn, dan hoef je misschien geen commentaar te schrijven. Maar soms kun je toch nog wat toevoegen:

    # bereken gemiddelde cijfer voor deze student
    average = sum / assignment_count + 1

(Nu weten we dat het niet zomaar om een gemiddelde gaat, maar om een cijfer. Afhankelijk van de rest van het programma heeft dit commentaar toegevoegde waarde.)

#### Schrijfwijze

Let ook op de schrijfwijze: geen hoofdletter, geen punt, en een spatie na het hekje `#`. Het commentaar staat *boven* de regel waar het over gaat.

### Voorbeeld 2

Het is gebruikelijk om bovenaan programma's wat algemene informatie op te nemen. Meestal gaat het om de namen van de auteurs, en een samenvatting van het doel van het programma.

    # Name: Jane Lee
    # Collaborators: John Doe
    #
    # This program calculates the average values of a series
    # of numbers input by the user.

#### Schrijfwijze

Let ook hier even op de schrijfwijze. De samenvatting in het commentaar hierboven is toch wat te lang om op één enkele regel op te nemen. In dat geval moeten we het expliciet over meerdere regels verdelen. Gewoon een regel toevoegen met een `#` ervoor.

We hebben ervoor gekozen om het nu na ongeveer 60 tekens af te kappen. De bedoeling is dat regels een redelijke lengte hebben: lezen gaat het prettigst als regels zo'n 45--90 tekens lang zijn, net als in boeken.

## Indentatie

Indentatie gaat over het toevoegen van witruimte aan het begin van een regel. In Python is het in veel gevallen noodzakelijk om een regel te beginnen met spaties, bijvoorbeeld als je een functie definieert:

    def sum(x, y):
        result = x + y
        return result

Let wel op! Je kunt de extra witruimte invullen met tabs of met spaties. In heel veel gevallen is een tab zichtbaar als 8 spaties, maar soms ook als 4 of 2. Hoe dan ook, het wordt een probleem als je tabs en spaties door elkaar gaat gebruiken, want dan is onduidelijk wat de bedoeling is.

    def sum(x, y):
        result = x + y     # vier spaties
            return result  # 1 tab is hier 8 spaties geworden

De `return` staat een stukje extra naar rechts, maar in feite is het één tab. Het resultaat is dat het een stuk moeilijker leesbaar is. Bovendien begrijpt Python er ook niet zoveel meer van. Je krijgt al snel een foutmelding als je zoiets doet. Gebruik dus alleen maar spaties, of alleen maar tabs om te indenteren.

Oh, en misschien goed om nog even te herhalen. Als een regel eindigt op een dubbele punt (`:`), dan moeten alle regels eronder geïndenteerd worden. Tenminste, de regels die er inderdaad bij horen.

    def sum(arrayOfNumbers):
        result = 0
        for number in arrayOfNumbers:
            result = result + number
        return result

Hier zie je dat de regel `result = result + number` bij de `for`-loop hoort. De `return` staat echter weer een stukje naar links, waardoor je weet dat deze niet bij de `for`-loop hoort.

## Naamgeving

Veel elementen in je code hebben een *naam*. Het gaat dan vooral om functies en variabelen. We geven wat richtlijnen.

### Functies

De namen van functies mogen zo lang zijn als je wilt, mits redelijk. In dit geval is het belangrijk dat het doel van de functie zo duidelijk en precies mogelijk omschreven wordt.

    def user_average_this_year():
        ...

Je ziet dat in de naam meerdere woorden staan, die gescheiden zijn met een underscore (`_`). Dit is gebruikelijk in Python, alle functienamen met meerdere woorden zijn geschreven met kleine letters en met underscores ertussen.

### Variabelen

Namen van variabelen hou je het liefst net wat korter dan functienamen, omdat ze meestal vaker voorkomen. Denk dan aan één of twee woorden. Een paar voorbeelden:

    wall_height = 2.34
    earth_circumference = 40007.86
    total_rainfall = 823.3

Woorden afkorten is meestal niet de bedoeling. Hiervan wordt je code een stuk lastiger te lezen (een erg luie programmeur zou bovenstaande variabelen wellicht `wh`, `ecirc` en `t_rain` hebben genoemd, maar hoe moet je nog achterhalen wat daar bedoeld wordt?).

Er zijn uitzonderingen. Je programma gaat namelijk weleens over een bepaald onderwerp waar afkortingen gebruikelijk zijn. Wiskunde en natuurkunde hebben dit natuurlijk wel vaker. 

    v_rabbit = 0.002            # v is for "velocity"
    x_rabbit = 23.11            # x is for "displacement"

Toch zie je dat we de uitleg er wel bij moeten zetten, dus het is een goed idee om de afkortingen zoveel mogelijk te vermijden tenzij het evident is wat bedoeld wordt.

## Witregels en extra spaties

Net als in andere media waarin tekst een belangrijke rol speelt, kan in programma's witruimte worden ingezet om de leesbaarheid te vergroten.

### Witregels

Zoals hierboven beschreven bij "commentaar" kun je je programma vaak opdelen in blokjes code. Hiermee kun je bijvoorbeeld de verschillende stappen beschrijven in een algoritme. Zie hier een programma dat in drieën gesplitst is:

    number = input("Please enter a number: ")
    while number < 0:
        number = input("Please enter a *positive* number: ")
    
    # calculations: uses a complex loop to handle special cases
    while(number > 0):
        number -= 1
    if number == 0:
        number += 1
    
    # output: might not print zero (e.g., if user put in a float)
    print(user_input)

De drie onderdelen zijn respectievelijk: de gebruikersinvoer, de berekening, en de uitvoer. Die onderdelen kom je wel vaker tegen natuurlijk. Let ook op de aanwijzingen die we in het commentaar hebben toegevoegd: eerst uitleg van complex algoritme, daarna een waarschuwing dat het misschien niet altijd werkt (en vooral: wanneer!).

### Spaties rondom operatoren

Operatoren zoals `+`, `==`, `%` en `**` zijn veelgebruikt in formules en vergelijkingen. Het is de bedoeling om hier heel bewust spaties rondom de operatoren te plaatsen, zodat we formules goed leesbaar blijven:

    i = i + 1
    submitted += 1
    x = x * 2 - 1
    hypotenuse_squared = x * x + y * y
    c = (a + b) * (a - b)
