# Number Guessing Game
- This program is a simple game based on a very simple concept. The computer will generate a number based upon a range provided by the player, and it is the players goal to guess that number. 
- If the player guesses too high or too low, the program will tell them as such, and allow them to guess again
- If the player inputs an invalid range or guess, the program will request that they try again
```mermaid
flowchart TD
  range([Request range from user]) --> gen
  range --> rangeError([if input is not a valid range])
    rangeError --> rangeError2([print 'Input is not a valid range. Try again!'])

  gen([Generate random number from specified range]) --> input([Request number input from user])
  input --> validate([Validate input number])

  validate --> low([Input number is too low]) 
  validate --> correct([Input number is correct]) 
  validate --> high([Input number is too high]) 
  validate --> error([Input is not a valid integer])

  low --> pr1([print 'Your number is too low. Try again!'])
  correct --> pr2([print 'Correct!'])
  high --> pr3([print 'Your number is too high. Try again!'])
  error --> error2([print 'your input was not a valid integer. Try again!'])

  error2 --> validate
  pr1 --> input
  pr3 --> input
```
