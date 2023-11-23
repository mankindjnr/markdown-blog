# DATA STRUCTURES AND ALGORITHMS IN PYTHON

## BINARY SEARCH
### question
Alice has some cards with numbers written on them. She arranges the cards in decreasing order, and lays them out face down in a sequence on a table. She challenges Bob to pick out the card containing a given number by turning over as few cards as possible. Write a function to help bob locate the card.

### Walkthrough
represent the cards in a list and accessing a value will represent flippig the card.
We need to access the given value with the least amount of iterations.

CARDS -> A list of numbers sorted in decreasing order.
QUERY -> The value we are searching for.
We will output position of the value given

```python
cards = [13, 11, 10, 7, 4, 3, 1, 0]
query = 7
output = 3

def locate_card(cards, query):
    pass
```

### Testing
```python
test = {
    "input": {
        "cards": [13, 11, 10, 7, 4, 3, 1, 0],
        "query": 7
    },
    "output": 3
    }

locate_card(test["input"]["cards"]) == test["output"]
locate_card(**test["input"]) == test["output"]
```

### solution one | BruteForce | LinearSearch
Create a variable position with the value 0
check whether the number at index position in card equals query
if it does, position is the answer and can be returned from the function
if not, increment the value of position by 1, and repeat steps 2 to 5 till we reach the last position
if the number was not found, return -1

```python
def locate_card(cards, query):
    position = 0

    while position < len(cards):
        if cards[position] == query:
            return position

        position += 1

    return -1
```

The BruteForce method is not an efficient way since it iterates N items.

### solution two | Binary Search |left <--> right solution
The question states that the cards are already sorted.
Randomly pick a card
check if the card given is greater or lesser than the randomly picked, this way you can either eliminate the bottom half or greater half. To do this pick the random card to be in the middle.

- __find the middle element of the list__
- __if it matches queried number, return the middle postion as the answer__
- __if it is less than the given number, then search the first half of the list__
- __if it is greater than the given number, then search the second half of the list__
. __repeat the above steps with the new half till solution__
- __if no more elements remain, return -1__

```python
def locate_card(cards, query):
    low, high = 0, len(cards) - 1

    while low <= high:
        mid = (low + high) // 2 # getting the middle index "//" for gettign an int instead of a float
        mid_number = cards[mid]

        if mid_number == query:
            return mid
        elif mid_number < query:
            high = mid - 1 # moving the high index to the middle since the greate half is no longer needed
        elif mid_number > query:
            low = mid + 1 # moving the lowest index to the middle since the bottom half is no longer needed

    return -1

"""
In case of multiple values matching the given query, we want to check if the value we have is the earliest occurence. For this, we are goin to check if thats the case with a test_location function..
"""

def test_location(cards, query, mid):
    mid_number = cards[mid]
    if mid_number == query:
        if mid-1 >= 0 and cards[mid-1] == query: # if the number on the left is equal, move left(mid-1 >= 0) ensuring tha the index exists first
            return 'left'
        else:
            return "found"

    elif mid_number < query:
        return "left"
    else: 
        return "right"

def locate_card(cards, query):
    low, high = 0, len(cards) - 1

    while low <= high:
        mid = (low + high) // 2 # getting the middle index "//" for gettign an int instead of a float
        mid_number = cards[mid]

        result = test_location(cards, query, mid)

        if result == "found":
            return mid
        elif result == "left":
            high = mid - 1 # moving the high index to the middle since the greater half is no longer needed
        elif result == "right":
            low = mid + 1 # moving the lowest index to the middle since the bottom half is no longer needed

    return -1
```
