# **Python-Game-Rock-paper-and-scissors vs. PC**
Hello! I continue my path as an apprentice (self-taught) programmer. The last few weeks I've been learning Python, and after learning how to define functions and use conditionals, I wanted to create a little game of "Rock, Paper, Scissors."

I show them my process and the code (Python). Thank you very much for your time!

## Whats the game about?

Rock, paper, scissors is a classic game for both children and adults. In the game, two people choose between three possibilities: rock, paper or scissors.

Depending on each person's choice, there can be three possible outcomes: defeat, draw or victory. The possible combinations are:
 
> 1. Rock vs Paper: paper wins, rock loses
> 2. Rock vs Scissors: rock wins, scissors lost
> 3. Paper vs Scissors: Scissors win, paper loses

If both players draw the same figure, it is a tie.

## What language do I use?

I have chosen Python since I am working and learning with it. The tool I used to test is Visual Studio Code.

Additionally, I have used the Python library "random" to be able to indicate random selections. So the first thing I did was import the library and name it to simplify the code:

```
import random as rd
```

## The "game" code

Once I imported the library, I started to "play".

The first thing was to define, through a function, the values for each hand. I use the **def** function to create a function called **choice** with three **if** conditionals to give a numerical value to each shape. I decide to use numbers, rather than the words themselves, to avoid problems with capitalization, lowercase, or typos.

The structure I have followed is: condition (**if**) if for variable (**a**) is exactly equal (**==**) to a value between 1 and 3, return a string.

```
def choice(a):
    if a == 1:
        return("Rock")
    if a == 2:
        return("Paper")
    if a == 3:
        return("Scissors")
```

The next step I followed is to create lines of text: one for the user's choice (you) and another for the PC's choice.

I define a function again, in this case called **text()**. This returns two **print()**, the one for the user and the one for the PC. To avoid type convenience errors, I use **f** notation so that variables enclosed in braces ({}) return the indicated value. In this case, the choice of each player.

Inside the braces I put the function created before **choice** to indicate the value that the user and the PC have chosen and I indicate the variable (**user** or **pc**) to the function.

```
def text():
    print(f"You have chosen: {choice(usuario)}")
    print(f"The PC has chosen: {choice(pc)}")
```
From this point, I start writing the interface code for the Terminal.

First, I indicate as a "title" a **print()** that announces the game: "Rock, paper, scissors' game".

Secondly, I name the **user** so that he can choose his option. For that, I use the **input()** function to enable text input for the user to choose between 1 (Rock), 2 (paper) or 3 (scissors). I use line breaks (**\n**) to make it look clearer in the terminal.

Additionally, I change the data type to **int** to avoid errors with the numbers.

I also write the line of code for the **PC** to choose its own hand. This is where I use the **random** library, named **rd**. To do this, I name the variable **pc** and through the randint function I tell it to generate a number between 1 and 3.

```
print("Rock, paper, scissors' game")
user = int(
    input("Choose: \n1 Rock \n2 Paper \n3 Scissors => "))
pc = rd.randint(1,3)
```


```
if pc == user:
    text()
    print("Tie :/")
elif (user == 1 and pc == 3) or (user == 2 and pc == 1) or (user == 3 and pc == 2):
    text()
    print("You win! :D")
elif (user == 1 and pc == 2) or (user == 2 and pc == 3) or (user == 3 and pc == 1):
    text()
    print("You lost! :(")
else:
        print("Please, choose a number between 1 and 3")
```

Now I write the line of code with the possible results that there are. Let's remember that there are three: defeat, draw and victory. To do this I establish three **if**:

> 1. Tie: if both **pc** and **user** have the same hand. I indicate this with an exactly equal (**==**).

>2. Win: I use the **elif** conditional (to check the condition if "Tie" is false) to indicate situations where the **user** wins.
To do this I establish three possible conditions using the **or** operator: the **user** selects 1 (Stone) **and** the **pc** selects 3 (Scissors), the **user** selects 2 (Paper) **and** the **pc** selects 1 (Rock) and the **user** selects 3 (Scissors) **and** the **pc** selects 2 (Paper).

> 3. Defeat: like the previous case, I also use **elif** and establish three conditions: the **user** selects 1 (Stone) **and** the **pc** selects 2 (Paper), the **user** selects 2 (Paper) **and** the **pc** selects 3 (Scissors) and the **user** selects 3 (Scissors) **and** the **pc** select 1 (Stone).

In each condition I indicate that it emits the function **text()** that prints the text written before with the choice of each player and a **print()** with the texts of: "Tie :/", "You win ! :D" and "You lost :(".

At the end, I set an **else** condition so that, in case the user chooses a number other than 1, 2 or 3, I output the text: "Please, choose a number between 1 and 3".

```
if pc == user:
    text()
    print("Tie :/")
elif (user == 1 and pc == 3) or (user == 2 and pc == 1) or (user == 3 and pc == 2):
    text()
    print("You win! :D")
elif (user == 1 and pc == 2) or (user == 2 and pc == 3) or (user == 3 and pc == 1):
    text()
    print("You lost! :(")
else:
        print("Please, choose a number between 1 and 3")
```

## Result

Once you run the complete code in the terminal (which I will put together later), the terminal displays the following message:

Choose:
1 Rock
2 Paper
3 Scissors => [here you write the number]

Based on the number you have chosen, it outputs a text and a result. This is an example in case you have typed 2 and the PC has "chosen" 1:

You have chosen: Paper
The PC has chosen: Rock
You win! :D

## Thanks

Thank you very much for coming this far. I continue my path learning programming and it is being very fun. I attach the complete code:

```
import random as rd

def choice(a):
    if a == 1:
        return("Rock")
    if a == 2:
        return("Paper")
    if a == 3:
        return("Scissors")
   
def text():
    print(f"You have chosen: {choice(user)}")
    print(f"The PC has chosen: {choice(pc)}")

print("Rock, paper, scissors' game")
user = int(
    input("Choose: \n1 Rock \n2 Paper \n3 Scissors => "))
pc = rd.randint(1,3)
if pc == user:
    text()
    print("Tie :/")
elif (user == 1 and pc == 3) or (user == 2 and pc == 1) or (user == 3 and pc == 2):
    text()
    print("You win! :D")
elif (user == 1 and pc == 2) or (user == 2 and pc == 3) or (user == 3 and pc == 1):
    text()
    print("You lost! :(")
else:
        print("Please, choose a number between 1 and 3")
```
