## f-string
Also called formatted string literals, is a new syntax of formatting string.

```Python
>>> name = str(input("Give me a name: "))
>>> print(f'Hello, my name is {name}')
Give me a name: nice
Hello, my name is nice
```

The earliest format was % (the percent sign) , which it used:
```Python
>>> name1 = 'Xiaohu'
>>> print('Hello %s' %name1)
'Hello Xiaohu'
```
% s means formatted as a string, with %d (decimal integer) andn %f (floating point) commonly used.
This usage is still widely used today, but it is actually a grammar that is not advocated for use.



---
***Exercise***

Hint - join() Function
myTuple = ("John", "Peter", "Vicky")
x = " ".join(myTuple)
print(x)
John Peter Vicky


```Python
>>> letter_to_morse = {
    'a':'.-', 'b':'-...', 'c':'-.-.', 'd':'-..', 'e':'.', 'f':'..-.',
    'g':'--.', 'h':'....', 'i':'..', 'j':'.---', 'k':'-.-', 'l':'.-..', 'm':'--',
    'n':'-.', 'o':'---', 'p':'.--.', 'q':'--.-', 'r':'.-.', 's':'...', 't':'-',
    'u':'..-', 'v':'...-', 'w':'.--', 'x':'-..-', 'y':'-.--', 'z':'--..',
    '0':'-----', '1':'.----', '2':'..---', '3':'...--', '4':'....-',
    '5':'.....', '6':'-....', '7':'--...', '8':'---..', '9':'----.', ' ':'/'
}

>>> message = "please help"

# `morse` is a list which will eventually contain the
# strings for each morse code letter in the message.
>>> morse = []
>>> for letter in message:
    morse_letter = letter_to_morse[letter]
    morse.append(morse_letter)

>>> morse_message = " ".join(morse)
>>> print(f"Incoming message: {message}")
>>> print(f"Morse encoded: {morse_message}")

Incoming message: please help
Morse encoded: .--. .-.. . .- ... . / .... . .-.. .--.
```
---
