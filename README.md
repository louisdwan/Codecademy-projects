# Codecademy-projects
grades = [100, 100, 90, 40, 80, 100, 85, 70, 90, 65, 90, 85, 50.5]

def print_grades(grades_input):
  for grade in grades_input:
    print grade

def grades_sum(scores):
  total = 0
  for score in scores: 
    total += score
  return total
    
def grades_average(grades_input):
  sum_of_grades = grades_sum(grades_input)
  average = sum_of_grades / float(len(grades_input))
  return average


def grades_variance(scores):
  average = grades_average(scores)
  variance = 0
  for score in scores:
    variance += (average - score) ** 2
  return variance / len(scores)


def grades_std_deviation(variance):
  return variance ** 0.5

variance = grades_variance(grades)
print grades_std_deviation(variance)

print print_grades(grades)
print grades_sum(grades)
print grades_average(grades)
print grades_variance(grades)
print grades_std_deviation(variance)

*************************************
"""
This program generates passages that are generated in mad-lib format
Author: Louis
"""

# The template for the story

STORY = "This morning %s woke up feeling %s. 'It is going to be a %s day!' Outside, a bunch of %ss were protesting to keep %s in stores. They began to %s to the rhythm of the %s, which made all the %ss very %s. Concerned, %s texted %s, who flew %s to %s and dropped %s in a puddle of frozen %s. %s woke up in the year %s, in a world where %ss ruled the world."

print 'Story is beginning'

name = raw_input("Enter a name: ")
adj1 = raw_input("Enter an adjective: ")
adj2= raw_input("Enter an adjective: ")
adj3= raw_input("Enter an adjective: ")
verb= raw_input("Enter a verb: ")
noun1= raw_input("Enter a noun: ")
noun2= raw_input("Enter a noun: ")
animal= raw_input("Enter an animal: ")
food= raw_input("Enter a food: ")
fruit= raw_input("Enter a fruit: ")
superhero= raw_input("Enter a superhero: ")
country= raw_input("Enter a country: ")
dessert= raw_input("Enter a dessert: ")
year= raw_input("Enter a year: ")

print STORY % (name, adj1, adj2, animal, food, verb, noun1, fruit, adj3, name, superhero, name, country, name, dessert, name, year, noun2)
******************************************************************************
#This app is used to calculate the area of many shapes. rate my code
print "Calculator is starting."

option = raw_input("Enter C for Circle or T for Triangle: ")
if option == 'C':
  radius = float(raw_input("What is the radius? "))
  area = 3.14159 * radius ** 2
  print str(area)
elif option == 'T':
  base = float(raw_input("What is the base? "))
  height = float(raw_input("What is the height? "))
  area = .5 * base * height
  print str(area)
else: print"Invalid Shape"
***************************************************************************
pyg = 'ay'

original = raw_input('Enter a word:')

if len(original) > 0 and original.isalpha():
  word = original.lower()
  first = word[0]
  new_word = word + first + pyg
  new_word = new_word[1:len(new_word)]
  
  print new_word
else:
  print 'empty'
**************************************************************************
"""Roll a pair of dice, guess the combination you win!"""
from random import randint
from time import sleep

def get_user_guess():
  guess = int(raw_input("Guess a number:  "))
  return guess

def roll_dice(number_of_sides):
  first_roll = randint(1, number_of_sides)
  second_roll = randint(1, number_of_sides)
  max_val = number_of_sides * 2
  print "The maximum possible value is: %d" % max_val
  guess = get_user_guess()
  if guess > max_val:
    print "That guess is too large, try a smaller number"
  else: print "Rolling"
  sleep(2)
  print "The first roll is %d" % first_roll
  sleep(1)
  print "The second roll is %d" % second_roll
  sleep(1)
  total_roll = first_roll + second_roll
  print "The total value of the roll is %d" % total_roll
  print "Result..."
  sleep(1)
  if guess == total_roll:
   print "Congratulations you won!"
  else: print " You Lost!"
    
    
roll_dice(6)
*************************************************************************
'''This will simulate a game of rock, paper, scissors '''
from random import randint
options = ["Rock","PAPER","SCISSORS"]
message ={
  "tie": "Yawn it's a tie!",
  "won": "Yay you won!",
  "lost": "Aww you lost!"
}
def decide_winner(user_choice, 
computer_choice):
  print "You selected %s" % user_choice
  print "Computer selected %s" % computer_choice
  if user_choice == computer_choice:
    print message["tie"]
  elif user_choice == options[0] and computer_choice == options[2]:
    print message["won"]
  elif user_choice == options[1] and computer_choice == options[0]:
    print message["won"]
  elif user_choice == options[2] and computer_choice == options[0]:
    print message["won"]
  else:
    print message["lost"]
    
def play_RPS():
  print "Rock, Paper, or Scissors?"
  user_choice = raw_input("Enter Rock, Paper or Scissors: ")
  user_choice = user_choice.upper()
  computer_choice = options[randint(0, 2)]
  decide_winner(user_choice, computer_choice)

play_RPS()
  
*****************************************************************
lloyd = {
  "name": "Lloyd",
  "homework": [90.0, 97.0, 75.0, 92.0],
  "quizzes": [88.0, 40.0, 94.0],
  "tests": [75.0, 90.0]
}
alice = {
  "name": "Alice",
  "homework": [100.0, 92.0, 98.0, 100.0],
  "quizzes": [82.0, 83.0, 91.0],
  "tests": [89.0, 97.0]
}
tyler = {
  "name": "Tyler",
  "homework": [0.0, 87.0, 75.0, 22.0],
  "quizzes": [0.0, 75.0, 78.0],
  "tests": [100.0, 100.0]
}

# Add your function below!
def average(numbers):
  total = float(sum(numbers))
  total = total / len(numbers)
*******************************************************************************
from random import randint

board = []

for x in range(0, 5):
  board.append(["O"] * 5)

def print_board(board):
  for row in board:
    print " ".join(row)

print_board(board)

def random_row(board):
  return randint(0, len(board) - 1)

def random_col(board):
  return randint(0, len(board[0]) - 1)

ship_row = random_row(board)
ship_col = random_col(board)



# Everything from here on should be in your for loop
# don't forget to properly indent!
for turn in range(4):
  print "Turn", turn + 1
  guess_row = int(raw_input("Guess Row: "))
  guess_col = int(raw_input("Guess Col: "))


  if guess_row == ship_row and guess_col == ship_col:
    print "Congratulations! You sank my battleship!"
    break
  else:
    if guess_row not in range(5) or \
      guess_col not in range(5):
      print "Oops, that's not even in the ocean."
    elif board[guess_row][guess_col] == "X":
      print( "You guessed that one already." )
    else:
      print "You missed my battleship!"
    if turn == 3:
      print "Game Over"
    else:  
      board[guess_row][guess_col] = "X"
    print_board(board)
    ********************************************************************
    #This is a calendar that will print a message, delete an event on calendar, shouldn't terminate unless the user decides

from time import sleep, strftime
name = "Louis"
calendar = {}
def welcome():
  print "Welcome to Calendar " + name 
  print "Calendar is opening"
  sleep(1)
  print "Today is " + strftime("%A, %d %B, %Y")
  print "The time is " + strftime("%H:%M:%S")
  sleep(1)
  print "What would you like to do?"
  
def start_calendar():
  welcome()
  start = True
  while(start):
    user_choice = raw_input("A to Add, U to Update, V to View, D to Delete, X to Exit: ")
    user_choice.upper()
    if user_choice == "V":
        if calendar.keys().len() < 1:
          print "The Calendar is Empty!"
        else: print calendar
    elif user_choice == "U":
      date = raw_input("What date? ")
      update = raw_input("Enter the update: ")
      calendar[date] = update
      print "Update was successful!"
      print calendar
    elif user_choice == "A": 
      event = raw_input("Enter event: ")
      date = raw_input("Enter date (MM/DD/YYYY): ")
      if len(date) > 10 or int(strftime("%Y")) > int(date[6:]):
        print "An invalid date was entered"
        try_again=raw_input("Try Again? Y for Yes, N for No: ")
        try_again.upper()
        if try_again == Y:
          continue
        else: start = False
      else: calendar[date] = event
    elif user_choice == "D":
      if calendar.keys().len() < 1:
        print "The calendar is empty!"
      else: 
        event = raw_input("What event?")
        for date in calendar.keys:
          if events == calendar[date]:
            del calendar[date]
            print "event was successfully deleted"
            print calendar
          else: print "An incorrect event was specified"  
    elif user_choice == "X":
      start = True
    else: print "An invalid command was entered!"  
      
start_calendar()
print calendar

******************************************************************************
grades = [100, 100, 90, 40, 80, 100, 85, 70, 90, 65, 90, 85, 50.5]

def print_grades(grades_input):
  for grade in grades_input:
    print grade

def grades_sum(scores):
  total = 0
  for score in scores: 
    total += score
  return total
    
def grades_average(grades_input):
  sum_of_grades = grades_sum(grades_input)
  average = sum_of_grades / float(len(grades_input))
  return average


def grades_variance(scores):
  average = grades_average(scores)
  variance = 0
  for score in scores:
    variance += (average - score) ** 2
  return variance / len(scores)


def grades_std_deviation(variance):
  return variance ** 0.5

variance = grades_variance(grades)
print grades_std_deviation(variance)

print print_grades(grades)
print grades_sum(grades)
print grades_average(grades)
print grades_variance(grades)
print grades_std_deviation(variance)
