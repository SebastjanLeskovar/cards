# Notes

## Types of languages

Dynamic types

Javascript, Ruby, Python

We do not care what values we are assigning to any given variable. 

Static types

C++, Java, Go

When we define a variable, we assign it a type.

## basic Go types

Type        Example
-----------------------------------------
bool        true, false
string      "Hi!", "How is it going?"
int         0, -10000, 99999
float64     10.000001, 0.00009, -100.003

## Functions

Define a function: 

```
func newCard() string {
    return "Five of Diamonds"
}
```

Functions must define return type. 

## Arrays and slices

Arrays have fixed length while slices do not. They can contain only one type of elements.

Declare a slice:

```
cards := []string {"Ace of Diamonds", newCard()}
```

Add a new string:

cards = append(cards, "Six of Spades")

## Iteration

```
for i, card := range cards {
    fmt.Println(i, card)
}
```

## Receiver function

```
func (d deck) print() {

}
```

d = the vorking variable / the actual copy of the deck we are working with is available as a variable called 'd'. In Python, the equivalent of 'd' is self. 

This receiver function is of type 'deck' and the function name is deck. Receiver sets up methods on variables that we create.

Any variable of type 'deck' now gets access to the 'print' method. 

## Slice range syntax

fruits = ["apple", "banana", "grape", "orange"]

fruits[StartIndexIncluding: upToNotIncluding]

fruits[0:2] = ["apple", "banana"]

## Multiple return values

func deal(d deck, handSize int) (deck, deck) {
	return d[:handSize], d[handSize:]
}

## Byte slices

Library ioutil enables us to write files to drive and load them.

`func WriteFile(filename string, data []byte, perm os.FileMode) error`

Function WriteFile is used to create or write to a new or existing file on local hard drive.

### Byte slice

"Hi there!" => string

[72 105 32 116 104 101 114 101 33] => byte slice

## Type conversion

[]byte("Hi there!")

Here, we turn the string "Hi there!" into a bite slice. 

## Tests

Tests are written in files named <filename>_test.go. 

