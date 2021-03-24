import art
import random
from game_data import data
from replit import clear



#FUNCIONES:
#funcion para elegir un pj random de la lista:
def random_character(data):
  character = {}
  random_index = random.randint(0, len(data)-1)
  character= data[random_index]
  data.pop(random_index)
  return character

#funcion para comparar valores y retornar el resultado (gana o pierde):
def compare_values(a_char, b_char, user_input):
  user_win = False
  a_option = 'a'
  b_option = 'b'
  if a_char['follower_count'] > b_char['follower_count']:
    if user_input == a_option:
      user_win = True
  elif a_char['follower_count'] < b_char['follower_count']:
    if user_input == b_option:
      user_win = True
  return user_win


#variables fuera del ciclo
a_char = random_character(data)
b_char = random_character(data)
score = 0
wrong_message = f"Sorry, that's wrong. Final score: {score}."
right_message = f"You're right! Current score: {score}."
empty_list = "We ran out of characters! Thank you for playing."
playing = True

#Ciclo
while playing:
  a_compare = f"Compare A: {a_char['name']} a {a_char['description']} from {a_char['country']}.\n"
  b_compare = f"Against B: {b_char['name']} a {b_char['description']} from {b_char['country']}.\n"
  print(art.logo)
  #pantalla con prints
  if score != 0:
    print(f"You're right! Current score: {score}.")
  print(a_compare)
  print(art.vs)
  print(b_compare)
  #eleccion del usuario
  user_input = input("Who has more followers? Type 'A' or 'B': ").lower()
  #se comparan los followers y devuelve el resultado
  result = compare_values(a_char, b_char, user_input)
  #resultado
  if result == True:
    score += 1
    if data == []:
      print(empty_list)
      playing = False
    clear()
    a_char = b_char
    b_char = random_character(data)
  else:
    print(f"Sorry, that's wrong. Final score: {score}.")
    playing = False

