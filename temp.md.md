# Codecademy:Classes
Notes from Learn Python3 lesson in Codecademy
## Constructors

There are several methods that we can define in a Python class that have special behavior. These methods are sometimes called “magic”, because they behave differently from regular methods. Another popular term is _dunder methods_, so-named because they have two underscores (double-underscore abbreviated to “dunder”) on either side of them.

The first dunder method we’re going to use is the `__init__` method (note the two underscores before and after the word “init”). This method is used to _initialize_ a newly created object. It is called every time the class is instantiated.

Methods that are used to prepare an object being instantiated are called _constructors_. The word “constructor” is used to describe similar features in other object-oriented programming languages but programmers who refer to a constructor in Python are usually talking about the `__init__` method.
```py
class Shouter:
  def __init__(self):
    print("HELLO?!")

shout1 = Shouter()
# prints "HELLO?!"

shout2 = Shouter()
# prints "HELLO?!"
```

Above we created a class called `Shouter` and every time we create an instance of `Shouter` the program prints out a shout. Don’t worry, this doesn’t hurt the computer at all.

Pay careful attention to the instantiation syntax we use. `Shouter()` looks a lot like a function call, doesn’t it? If it’s a function, can we pass parameters to it? We absolutely can, and those parameters will be received by the `__init__` method.

```py
class Shouter:
  def __init__(self, phrase):
    # make sure phrase is a string
    if type(phrase) == str:

      # then shout it out
      print(phrase.upper())

shout1 = Shouter("shout")
# prints "SHOUT"

shout2 = Shouter("shout")
# prints "SHOUT"

shout3 = Shouter("let it all out")
# prints "LET IT ALL OUT"
```
Above we’ve updated our `Shouter` class to take the additional parameter `phrase`. When we created each of our objects we passed an argument to the constructor. The constructor takes the argument `phrase` and, if it’s a string, prints out the all-caps version of `phrase`.

## String Representation

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTI5MzcxNzM3LC0yMDgyNDg0ODI4XX0=
-->