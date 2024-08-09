# Python Basics: Making the Game Multi-Player on One Device


# Introduction to Functions and Classes

## Functions



## Classes

```python
class Player:
    def __init__(self, name):
        self.name = name
        self.score = 0
        self.current_guess = 0
        self.guess_attempts = 0
        
player = Player()
player_2 = Player('Willie')
player_3 = Player('Nellie')
player_4 = Player('Ketty')
player_5 = Player('Eithel')

        
class GuessingGame:
    def __init__(self, lower_limit, upper_limit):
        ...
    
    def display_guess_hint_digit(self):
        str(self.random_number)[0]
```
