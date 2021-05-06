import sys,time,os
from random import randint
from datetime import datetime
# Code Nation
# Green Team Game

# global variables
game_name = "Destiny"
player_name = ""
total_points = 0
high_score = 0
play = True # if this variable changes to False, stop our main loop
death_reason = ""

# lists
path_options = []
#scores = []

# debug functions
def print_path_options():
    print("Debug!")
    i = 1
    for option in path_options:
        print(1, option) # print every item in the list
        i += 1

# functions
def cls(): # clear screen/terminal
    os.system('cls' if os.name=='nt' else 'clear')

def sprint(str): # print slowly function
    for c in str + '\n': 
        sys.stdout.write(c) # print 1 letter at a time
        sys.stdout.flush() # clear the print buffer
        time.sleep(0.01) # time delay

def sprint2(str): # workaround slow print function
    for c in str + '\n':
        print(c, end = '') # end = '' prevents print from creating a new line
        time.sleep(0.01) # time delay

def random_roll(minpoint,maxpoint):
    return randint(minpoint,maxpoint) # returns a random integer between minpoint and maxpoint

# end of functions

# start of story

def print_welcome():
    sprint("╔══════════════════════════════════════════════════════╗")
    sprint("║             Welcome to your Destiny                  ║")
    sprint("║          Developed by the \033[0;32mGreen Team\033[0;37;40m                 ║")
    sprint("║         In association with CodeNation               ║")
    sprint("║                      2021                            ║")
    sprint("╚══════════════════════════════════════════════════════╝\n")
    sprint("""""""""""""""""""""""""""
        _____            _   _             
       |  __ \          | | (_)            
       | |  | | ___  ___| |_ _ _ __  _   _ 
       | |  | |/ _ \/ __| __| | '_ \| | | |
       | |__| |  __/\__ \ |_| | | | | |_| |
       |_____/ \___||___/\__|_|_| |_|\__, |
                                       _/ |
                                      |___/ 
    
    
    
    
    """"""""""""""""""""""""""""\nIn a land terrorized by an evil despot King, you find yourself captured and at his mercy.\nWill you find a way to escape the roll of fate and realise your true Destiny?\nWill your EVERY choice lead you to success?\nor Will you die trying......\n\n")

def get_player_name():
    sprint(" \033[1;33mPlease enter your name:\033[0;37;40m \n")
    global player_name # access global variables
    player_name = "" # clear the player name
    while player_name == "": # run the loop until the player enters a name
        player_name = input() # gets the player name
        if player_name.lower() == "": # name can't be empty
            sprint("Sorry, I didn't get that.")
            sprint("Please enter your name:\n")
        if player_name.lower() == "will":
            sprint("\nWhere theres a will theres a way\n\n")
        if player_name.lower() == "pedro":
            sprint("\nOlá Pai\n")
        if player_name.lower() == "toby":
            sprint("\nThe original G with ALLLLL the fluff\n")
        if player_name.lower() == "geoff":
            sprint("\nMy name Jeff\n")
        if player_name.lower() == "keira":
            sprint("\nDon't you mean Kiera?\n")

def ready_to_play():
    global player_name
    reply_ok = False # changes to True if the player chooses yes or no
    nos_counter = 0 # number of NOs
    sprint("\n\033[1;33mHello {}, are you ready to play\033[0;37;40m (yes/no)?\n".format(player_name))
    while reply_ok == False: # loop until the player chooses yes or no
        option = input() # get the player choice
        if option.lower() == "no": 
            nos_counter += 1 # update our variable
            if nos_counter > 3:
                reply_ok = True # we have a correct reply from the player
                sprint("I knew you weren't worthy anyway\n")
                quit() # end our program after 3 NO
            else:
                sprint("\033[1;33mWould you like to reconsider?\n")
        elif option.lower() == "yes":
            reply_ok = True # we have a correct reply from the player
            male_or_female() # start the game / print first question
        else:
            sprint("""I didn't quite get that.
            Please try again!""")

def path_select():
    global total_points
    reply_ok = False
    while reply_ok == False: # loop until the player chooses an option
        option = (input())
        if option == "1" or option == "2":
            reply_ok = True # we have a valid reply
            sprint("\nWelcome Adventurer!\n")
            sprint("You have {} points.\n".format(total_points))
            sprint("Play through the story to collect (or lose) points from each decision.\n\n\n")
            path_options.append("a" + option)
            return option
        else:
            sprint("Sorry, I didn't get that.\n")

def male_or_female(): 
    sprint("\n\033[1;33mAre you a brave warrior knight?\033[0;37;40m (1)")
    sprint("or?")
    sprint("\033[1;33mAre you a low-born serving girl?\033[0;37;40m (2)\n")
    path_select()

def game_over():
    global player_name, game_name, death_reason, play
    sprint ("""""""""""""""""""""""""""""""""""""""""""""""""""""""""
   ____                         ____                 
 / ____|                       / __ \                
| |  __  __ _ _ __ ___   ___  | |  | |_   _____ _ __ 
| | |_ |/ _` | '_ ` _ \ / _ \ | |  | \ \ / / _ \ '__|
| |__| | (_| | | | | | |  __/ | |__| |\ V /  __/ |   
 \_____|\__,_|_| |_| |_|\___|  \____/  \_/ \___|_|   
                                                     
                                                     """"""""""""""""""""""""""""""""""""""""""""""""""""")
    sprint("""Total points : {}
    
    Thank you {} for playing {}!\n""".format(total_points, player_name, game_name)) # do we need death_reason?
    play = False

def last_red():
    global death_reason
    sprint("""You enter the door and head down the corridor
    
    As you walk you begin to feel sleepy and realise you have been jinxed by Magick!
    As you walk further you get sleepier and sleepier until eventually you fall asleep.
    \n""")
    sprint("You were jinxed with Magick and fell asleep!\n You were recaptured and returned to your room.\n")
    game_over()

def good_knight():
    global death_reason
    sprint("The knight suddenly stirs to life and swings his two handed sword at you and cleaves you in twain.\n")
    sprint("The Knight cut you in two.\n")
    game_over()

def last_pink():
    print("""
              _,.
            ,` -.)
           ( _/-\\-._
          /,|`--._,-^|            ,
          \_| |`-._/||          ,'|
            |  `-, / |         /  /
            |     || |        /  /
             `r-._||/   __   /  /
         __,-<_     )`-/  `./  /
        '  \   `---'   \   /  /
            |           |./  /
            /           //  /
        \_/' \         |/  /
         |    |   _,^-'/  /
         |    , ``  (\/  /_
         \,.->._    \X-=/^
         (  /   `-._//^`
         `Y-.____(__}
          |     {__)
                ()
    """)
    sprint("A suit of black armor stands in the corridor before you, it towers above you, blocking your way. However, you can see daylight and a possible escape route behind it.\n")
    sprint("\033[1;33mDo you continue to freedom or go back to try a different path?\033[0;37;40m (continue/go back)\n")
    reply_ok = False
    while reply_ok == False: # loop until we have a valid choice
        choice = input()
        if choice.lower() == "continue":
            reply_ok = True # we have a valid reply
            good_knight()
        elif choice.lower() == "back":
            reply_ok = True # we have a valid reply
            last_red()
        else:
            sprint("Make a choice. (continue/back)")

def fifth_pink():
    sprint("\nYou leave the book and head through the purple door on the opposite end of the room.\n")
    fourth_purple()

# Previous section: "You enter the room, on a table before you is a weird looking book. Do you open it?"
def second_purple():
    roll = random_roll(0,9)
    if roll>-1 and roll<9 :
        # Go to last_red()
        last_red()
    else:
        end_game()
        # Go to "All the magic of your ancestors floods your body"

def fourth_pink():
    global total_points
    sprint("\nYou enter the room\n It is a long and wide room with book shelves around the edge, at the far end is a purple door\n On a raised dais before you is a mysterious looking book. It appears to pulsate with energy, a low humming seems to fill the room.\n")
    sprint("\033[1;33mDo you want to read the book?\033[0;37;40m (yes/no)\n ")
    reply_ok = False
    while reply_ok == False: # loop until we have a valid reply
        option = input()
        if option.lower() == "yes" and path_options[0] == "a1": # a1 = male
            reply_ok = True # we have a valid reply
            sprint("\nYou open the book and nothing seems to happen.\n")
            total_points += 100
            second_purple()
        elif option.lower() == "yes" and path_options[0] == "a2": # a2 = female
            reply_ok = True # we have a valid reply
            end_game()
        elif option.lower() == "no":
            reply_ok = True # we have a valid reply
            fifth_pink()    
        else:
            sprint ("Please choose a path. (yes/no)")   # loops back

# Previous section: "You stumble through the door and find yourself face to face with a lion"
def third_purple():
    global total_points
    roll = random_roll(0,9)
    sprint("""
    You escape!
    You head back to the courtyard.\n
    """)
    if roll>-1 and roll<5: # if the number is between 0 and 4
        total_points += 100
        print('A huge black suit of armor towers above you, you see there is an exit behind him\n')
        last_pink() # Go forward to "A knight in black armor stands before you"
    else:
        total_points -= 100
        last_red()

        # Go right to last_red()

def first_blue():
    global death_reason,total_points
    cls() # clear the screen
    print("""
    You stumble through the door and find yourself face to face with a lion!
    however, he appears to be asleep....
        \|\||
       -' |||/
      /7   |||/
     /    |||||/
     \-' |||||||/`-.____________
      -|||||||||           /    `.
        |/||||             \      |
 _______/    /_       ______\      |__________-
(,__________/  `-.___(,_____________----------_)
    
    \n""")
    sprint('\n\033[1;33mDo you want to sneak past or run away?\033[0;37;40m (sneak/run)\n')
    reply_ok = False
    while reply_ok == False: # loop until we have a valid reply
        choice = input()
        if choice.lower() == "sneak":
            total_points -= 200
            reply_ok = True
            sprint('\nThe lion wakes up just as you begin to pass him, and pounces upon you, killing you instantly.\n')
            # Go to game over
            sprint("You were killed by a single swipe from the lion.\n")
            game_over()
        elif choice.lower() == "run":
            total_points += 100
            reply_ok = True
            sprint('\nYou manage to run away from the lion.\n')
            fourth_purple()
        else:
            print ("\nPlease choose your path: (sneak/run)\n")

def fourth_purple():
    global total_points
    cls() # clear the screen
    sprint("""
    \nContinuing down the stairs ahead of you, you find yourself in a wide empty courtyard, around the edge of the courtyard stands three doors.
On the left is what looks to be a latticework door made of wood and metal, it is painted a dirty white colour. It looks old.
Directly ahead of you stands a large wooden door painted black. The paint looks fresh.
And on the right stands a door that has been painted a bright purple colour. The paint is only slightly dulled.
    \033[1;33mWhich door do you wish to go through?\033[0;37;40m :
    
     (white)                   (black)                     (purple)
    \n""")
    reply_ok = False
    while reply_ok == False: # loop until we have a valid reply
        option=input()
        if option.lower() == 'white':
            total_points += 100
            reply_ok = True # we have a valid reply
            first_blue()
        elif option.lower() == 'black':
            total_points += 100
            reply_ok = True  # we have a valid reply
            last_pink()
        elif option.lower() == 'purple':
            total_points += 100
            reply_ok = True
            last_red()
        else:
            total_points -= 50
            sprint('Choose a path. (white/black/purple)')

def third_pink():
    global total_points
    sprint("\n\033[1;33mDirectly ahead of you, you find a huge golden door, it is ornate and has many precious gems embedded inside. Do you go through it?\033[0;37;40m  (yes/no)\n")
    reply_ok = False
    while reply_ok == False: # loop until we have a valid reply
        option = (input())
        if option.lower() == "yes":
            total_points += 100
            reply_ok = True # we have a valid reply
            path_options.append("d" + option)
            fourth_pink()
        elif option.lower() == "no":
            total_points += 50
            reply_ok = True # we have a valid reply
            path_options.append("d" + option)
            fourth_purple()
        else:
            sprint("Please choose your path.")

# Previous block = first_purple2 "You overpower the guards!"
def fifth_purple():
    global total_points
    reply_ok = False
    while reply_ok == False: # loop until we have a valid reply
        choice = input("\n\033[1;33mThere are stairs ahead of you. Do you go down them or go back?\033[0;37;40m  (down/back)\n")
        if choice.lower() == 'down':
            total_points += 100
            reply_ok = True # we have a valid reply
            sprint('\nYou proceed down the stairs\n')
            fluff_purple() # fourth_purple()
        elif choice.lower() == 'back':
            total_points += 50
            reply_ok = True # we have a valid reply
            sprint('\nYou turn around and return\n')
            third_pink()
        else:
            sprint("Make your decision")

def fluff_purple():
    global total_points
    reply_ok = False
    while reply_ok == False: # loop until we have a valid reply
        choice = input("\n\033[1;33mAs you go down the stairs you find a door ahead of you, it has a mythical creature carved into it. Do you go through the door?\033[0;37;40m (yes/no)\n")
        if choice.lower() == 'yes':
            total_points += 100
            reply_ok = True # we have a valid reply
            sprint("\nYou push open the door slowly and step into the gloom.\n") 
            sprint("Suddenly; torches in alcoves around the room blast into eye searing light, and before you stands a mighty Sphinx.\n")
            sprint("He looks at you ponderously for a while before he starts to speak. He asks you a riddle.\n")
            sprint("\033[1;33mWhat walks on four legs in the morning, two legs in the afternoon and three legs at night?\033[0;37;40m\n")
            if input() == ("man") or ("Man"):
                sprint ("You may pass")
                end_game()
            else:
                sprint ("You displease me human. Return from whence you came")
                fourth_purple()
        elif choice.lower() == 'no':
            total_points -= 50
            reply_ok = True # we have a valid reply
            sprint('\nYou return from where you came\n')
            fourth_purple()
        else:
            sprint("Make your choice. Or risk displeasing me.")

# Extra fluff - Previous block = first_purple2 "You see a glimmer of light"
def first_purple3():
    global death_reason, total_points
    reply_ok = False
    while reply_ok == False: # loop until we have a valid reply
        roll = random_roll(1,9)
        if roll>0 and roll<5: # if the number is between 1 and 4
            total_points += 50
            reply_ok = True # stop the first loop
            reply_ok2 = False # second loop
            while reply_ok2 == False: # loop until we have a valid reply
                sprint('\033[1;33mThe glimmer of light turns out to be a ring with a large red gemstone embedded, Do you pick it up?\033[0;37;40m (yes/no)\n')
                option = input()
                if option.lower() == 'yes':
                    total_points += 100
                    reply_ok2 = True # stop the loop
                    roll = random_roll(1,9)
                    if roll>0 and roll<5: # if the number is between 1 and 4
                        total_points -= 200
                        sprint("""\nThe ring shatters as you pick it up
                        \nYou continue down the path\n""")
                        fifth_purple()
                    else: # if the number is higher than 4
                        total_points += 1000
                        sprint("""\nYou pick up the ring
                        it turns out to be a golden ring with a ruby set inside!
                        \nYou continue down the path...\n""")
                        fifth_purple()
                elif option.lower() == 'no':
                    total_points += 200
                    reply_ok2 = True # stop the loop
                    sprint('\nYou continue down the path...\n')
                    fifth_purple()
                else:
                    sprint('Make a choice')
        else:  # if the number is higher than 4
            total_points += 100
            reply_ok = True # stop the first loop
            reply_ok3 = False
            while reply_ok3 == False: # loop until we have a valid reply
                choice=input('\n\033[1;33mThe glimmer of light turns out to be a small button embedded in the floor, Do you press it?\033[0;37;40m (yes/no)\n')
                if choice.lower() == 'yes':
                    total_points += 200
                    reply_ok3 = True # stop the loop
                    sprint("""\n\nYou press the button.
                    An alarm suddenly rings out and more guards appear
                    There were {} guards!\n\n""".format(roll))
                    #You were recaptured and returned to your cell\n\n
                    sprint("\nYou were recaptured and returned to your cell\n")
                    game_over()
                elif choice.lower() == 'no':
                    total_points += 50
                    reply_ok3 = True
                    sprint('\nYou continue down the path...')
                    fifth_purple()
                else:
                    sprint('Make a choice. (yes/no)')

# Extra fluff - Previous block = first_purple "You overpower the guards!"
def first_purple2():
    global total_points
    reply_ok = False
    while reply_ok == False: # loop until we have a valid reply
        choice=input("\n\033[1;33mYou see a glimmer of light on the ground near one of the unconscious guards, Do you inspect it?\033[0;37;40m (yes/no)\n")
        if choice.lower() == 'yes':
            total_points += 100
            reply_ok = True # we have a valid reply
            sprint('\nYou cautiously inspect the light...\n')
            first_purple3()
        elif choice.lower() == 'no':
            total_points -= 50
            reply_ok = True # we have a valid reply
            sprint('\nYou ignore the light and cautiously move forward.\n')
            fifth_purple()
        else:
            sprint("Make a choice.")

# Previous block = "The door is open! You enter the corridor. Turn right or left?"

def first_purple():
    global death_reason,total_points
    message = ""
    message2 = ""
    sprint('\nAs you round the corner there are guards standing before you, let the roll of fate decide how many stand in your way.\n')
    roll = random_roll(1,9)
    if roll>0 and roll<5: # Roll between 1-4 to overpower them
        if roll == 1:
            message = "was 1 guard"
            message2 = "him"
        else:
            message = "were {} guards".format(roll)
            message2 = "them"
        sprint('\nThere {}!\n\nYou manage to overpower {} and move forward.\n'.format(message,message2))
        first_purple2()
        total_points += 1000
    else:   # Roll 5-9 you're captured and returned to cell
        # Return to beginning 
        sprint('\nThere were {} guards!\nYou were captured and returned to your cell\n'.format(roll))
        #total_points = 0
        #death_reason = "\nYou were captured and returned to your cell\n"
        #quit()
        game_over()

def second_pink():
    global total_points
    door_locked = True
    while door_locked == True: # loop until the door is unlocked
        roll = random_roll(1,10)
        print("""
        Try the door.\n""")
        if roll>0 and roll<6: # if the number is between 1 and 5
            door_locked = False # door is open
            sprint("\nIt's open!\n")
            sprint("You enter the corridor beyond, there are three options open to you.\n")
            sprint("\n\033[1;33mTurn right, left or inspect mirror?\033[0;37;40m (right/left/mirror)\n")
            reply_ok = False
            while reply_ok == False: # loop until we have a valid reply
                option = input()
                if option.lower() == "right":
                    total_points += 100
                    reply_ok = True
                    path_options.append("c" + option) # add the option to our list
                    first_purple()
                elif option.lower() == "left":
                    total_points += 200
                    reply_ok = True
                    path_options.append("c" + option) # add the option to our list
                    third_pink()
                elif option.lower() == 'mirror':
                    total_points += 200
                    reply_ok = True
                    sm_1()
                else:
                    sprint("\033[1;33mPlease choose.\033[0;37;40m (right/left/mirror)\n")
        elif roll >5 and roll<11: # the door is locked
            sprint("Its locked.\n")
            pick_the_lock = 0 # counter
            try_again = False
            while try_again == False: # loop until we have a valid reply
                sprint("\n\033[1;33mTry to pick the lock?\033[0;37;40m (yes/no)")
                choice = input()
                if choice == "no":
                    sprint("You failed to escape from your cell.")
                    game_over()
                    door_locked = False # end door locked loop
                    try_again = True # end try again loop
                elif choice == "yes":
                    pick_the_lock += 1
                    if pick_the_lock < 6: # max attempts = 5
                        sprint("Oof")
                        try_again = True # breaks the loop
                    else: # player exceeded max attempts
                        sprint("You failed to unlock the door.")
                        game_over()
                        door_locked = False # end door locked loop
                        try_again = True # end try again loop
                else:
                    sprint("I didn't get that!")

def first_pink():
    global total_points
    sprint("\nYour character wakes up in a draughty room, the room is completely bare, the only furniture is the straw mattress you lie upon. Across the room is a barred window, and a large oak door stands closed on the other side.\n")
    sprint("What do you do first?\n")
    sprint("\n\033[1;33mGo to the window?\033[0;37;40m window")
    sprint("\033[1;33mGo to the door?\033[0;37;40m door\n")
    reply_ok = False
    while reply_ok == False: # loop util we have a valid reply
        option = input()
        if option.lower() == "window":
            reply_ok = True
            sprint("\nIt's very high up, no way you can get out of the window.\n")
            sprint ("\nSomething catches your eye on the window ledge. \nIts a hair pin!")
            total_points += 200
            path_options.append("b" + option)
            second_pink()
        elif option.lower() == "door":
            total_points += 200
            reply_ok = True
            second_pink()
        else:
            sprint("\033[1;33mPlease choose your path. window or door?\n")

## Strange mirror fluff section start

def sm_1():
    sprint("\nYou find a mirror covered in centuries of dust and cobwebs\n\n\033[1;33mDo you inspect it? (yes/no)\033[0;37;40m")
    reply_ok = False
    while reply_ok == False:
        option = input()
        if option.lower() == 'yes' or option.lower() == 'y':
            reply_ok = True
            sprint("\nYou wipe the dust and cobwebs off the mirror\nThe surface of the mirror shimmers like water, As you stare into the ever changing surface you begin to feel dizzy")
            sm_2()
        elif option.lower() == 'no' or option.lower() == 'n':
            reply_ok = True
            third_pink()
        else:
            sprint("Make a choice")

def sm_2():
    sprint("\nYou feel drawn towards the mirror\n\n\033[1;33mDo you touch the surface? (yes/no)\033[0;37;40m\n\n")
    reply_ok = False
    while reply_ok == False:
        option = input()
        if option.lower() == 'yes' or option.lower() == 'y':
            reply_ok = True
            sm_3()
        elif option.lower() == 'no' or option.lower() == 'n':
            reply_ok = True
            sm_21()
        else:
            sprint("Make a choice")

def sm_4():
    sprint("You wake up in a strange world, Things are different but also reversed.\nCould it be a mirror of the world from centuries ago?\n")
    sprint("\n\033[1;33mWill you explore this world? (yes/no)\033[0;37;40m\n")
    reply_ok = False
    while reply_ok == False:
        option = input()
        if option.lower() == 'yes' or option.lower() == 'y':
            reply_ok = True
            sm_5()
        elif option.lower() == 'no' or option.lower() == 'n':
            reply_ok = True
            sm_41()
        else:
            sprint("Try again")

def sm_3():
    sprint("\nThe surface of the mirror ripples like water as your hand sinks in\nSomething grabs your arm and pulls you into the mirror!\n")
    sprint("As you're pulled into the mirror the world begins to fade away and you pass out\n")
    sm_4()

def sm_5():
    sprint("\nAs you look around you notice something in the corner of your eyes.\nAs you try to focus on it the object darts around avoiding your gaze\n")
    sprint("\033[1;33mWill you try and interact with the object? (yes/no)\033[0;37;40m\n")
    reply_ok = False
    while reply_ok == False:
        option = input()
        if option.lower() == 'yes' or option.lower() == 'y':
            reply_ok = True
            sm_6()
        elif option.lower() == 'no' or option.lower() == 'n':
            reply_ok = True
            sm_51()
        else:
            sprint("Make a choice")

def sm_6():
    sprint("\nYou attempt to get closer and interact with the object but it quickly moves away; always at the edge of your vision\n")
    sprint("\033[1;33mIgnore the object and continue examining the area? (yes/no)\033[0;37;40m\n")
    reply_ok = False
    while reply_ok == False:
        option = input()
        if option.lower() == 'yes' or option.lower() == 'y':
            reply_ok = True
            sm_7()
        elif option.lower() == 'no' or option.lower() == 'n':
            reply_ok = True
            sm_61()
        else:
            sprint("Make a choice")

def sm_7():
    sprint("\nYou explore the area and find a single doorway\n")
    da_1()

def da_1():
    sprint("You approach the doorway, The door itself is completely gone and deep black scorch marks stain the frame and surrounding walls\n")
    sprint("\033[1;33mDo you enter? (yes/no)\033[0;37;40m\n")
    reply_ok = False
    while reply_ok == False:
        option = input()
        if option.lower() == 'yes' or option.lower() == 'y':
            reply_ok = True
            da_2()
        elif option.lower() == 'no' or option.lower() == 'n':
            reply_ok = True
            da_11()
        else:
            sprint("Make a choice")

def da_2():
    sprint("\nAs you cautiously pass through the doorway your vision shimmers and you find yourself in a forest\n")
    sprint("\033[1;33mDo you return or continue forward? (return/forward)\033[0;37;40m\n")
    reply_ok = False
    while reply_ok == False:
        option = input()
        if option.lower() == 'forward' or option.lower() == 'f':
            reply_ok = True
            fo_1()
        elif option.lower() == 'return' or option.lower() == 'r':
            reply_ok = True
            da_21()
        else:
            sprint("Make a choice")

def fo_1():
    sprint("\nYou continue walking through the forest\nYou slowly begin to realise that none of the trees are swaying. No leaves are falling and no birds are singing")
    sprint("\nEverything is silent except for the sound of your footsteps\n")
    sprint("\033[1;33mDo you continue? (yes/no)\033[0;37;40m\n")
    reply_ok = False
    while reply_ok == False:
        option = input()
        if option.lower() == 'yes' or option.lower() == 'y':
            reply_ok = True
            fo_2()
        elif option.lower() == 'no' or option.lower() == 'n':
            reply_ok = True
            fo_11()
        else:
            sprint("Make a choice")

def fo_2():
    sprint("\n\nAs you continue through the forest you begin to feel uneasy; Something isn't quite right\n")
    sprint("While you continue walking forward you notice an odd looking tree in the distance; It appears to be swaying slowly in a non-existant breeze\n")
    sprint("You walk towards the tree\n")
    tr_1()

def tr_1():
    sprint("\nAs you approach the tree you begin to notice a cave in the base that disappears deep into the earth")
    sprint("You look into the cave and feel a slight breeze coming out of the earth in a slow rythmic breathing pattern")
    sprint("You enter the cave and make your way into the earth.\nAs you delve deeper the breathing grows..\n")
    tr_2()

def tr_2():
    sprint("\nAs you stumble through the cave you notice a faint light coming from below.\nYour pace increases and your breathing deepens as you close in on the light")
    sprint("As you reach the light you begin to hear a ringing in your ears. As the sound grows louder the intensity of the light increases more and more")
    sprint("You shut your eyes to block out the light but it continues to blind you\n")
    tr_3()

def tr_3():
    sprint("Just as the pain becomes unbearable everything turns to darkness")
    sprint("You begin to wake up, Your eyes feel heavy and your head stings with pain")
    sprint("You find yourself on the floor in front of the mirror, Now shattered\n")
    sm_9()

def sm_9():
    sprint("As you begin to regain complete consciousness you notice a strange powder around the broken mirror. It glows faintly in the dim light\n")
    sprint("\033[1;33mInspect the mirror? (yes/no)\033[0;37;40m\n")
    reply_ok = False
    while reply_ok == False:
        option = input()
        if option.lower() == 'yes' or option.lower() == 'y':
            reply_ok = True
            sm_10()
        elif option.lower() == 'no' or option.lower() == 'n':
            reply_ok = True
            third_pink()
        else:
            sprint("Make a choice")

def sm_10():
    sprint("\nYou look over the broken shards of mirror and the strange glowing powder and find a small glass phial labelled with weird symbols and text\n")
    sprint("As you turn the phial around in your hands you recognise one of the words; It's an ingredient used for potions\n")
    sprint("Perhaps the glowing powder is residue of a potion from a long dead alchemist?\n")
    third_pink()

# Branching paths start

def sm_21():
    sprint("\nAs you begin to walk away from the mirror a shadow lashes out and grabs your arm")
    sprint("You try to resist the pull of the shadow but it's too strong")
    sprint("As the shadow pulls you below the mirrors surface you begin to lose consciousness\n")
    sm_4()

def sm_41():
    sprint("\nYou turn around only to find the mirror shattered into thousands of pieces\n")
    sm_5()

def sm_51():
    sprint("You ignore the object. Before long it disappears completely\n")
    sm_7()

def sm_61():
    sprint("\nYou continue trying to interact with the object only for it to disappear into a hole in the wall\n")
    sm_7()

def da_11():
    sprint("\nYou turn around to walk away when a shadow lashes out and pulls you through the doorway\n")
    sprint("The doorway disappears as soon as you pass through\n")
    sprint("You start walking forward\n")
    fo_1()

def da_21():
    sprint("\nYou turn around to return through the doorway only to watch it fade away into nothingness\n")
    sprint("You give up and continue moving forward\n")
    fo_1()

def fo_11():
    sprint("\nYou turn around to return and find a wall of interlocking trees blocking your return. Forcing you to continue further\n")
    fo_2()

# Branching paths end
### Strange mirror fluff section end

#Keira_section

def congratulations():
    global play,player_name,total_points,high_score,time_start # access global variables
    sprint("╔═══╗─────────────╔╗───╔╗───╔╗")
    sprint("║╔═╗║────────────╔╝╚╗──║║──╔╝╚╗")
    sprint("║║─╚╬══╦═╗╔══╦═╦═╩╗╔╬╗╔╣║╔═╩╗╔╬╦══╦═╗╔══╗")
    sprint("║║─╔╣╔╗║╔╗╣╔╗║╔╣╔╗║║║║║║║║╔╗║║╠╣╔╗║╔╗╣══╣")
    sprint("║╚═╝║╚╝║║║║╚╝║║║╔╗║╚╣╚╝║╚╣╔╗║╚╣║╚╝║║║╠══║")
    sprint("╚═══╩══╩╝╚╩═╗╠╝╚╝╚╩═╩══╩═╩╝╚╩═╩╩══╩╝╚╩══╝")
    sprint("──────────╔═╝║")
    sprint("──────────╚══╝")
    sprint("\nTotal points : {}".format(total_points))
    if total_points > high_score:
        sprint("NEW HIGH SCORE!")
        high_score = total_points
    time_end = datetime.now()
    print("Elapsed time :", time_end - time_start)
    sprint("\n\033[1;33mWould you like to play again?\033[0;37;40m (yes/no)\n")
    reply_ok = False
    while reply_ok == False: # loop until we have a valid reply
        option = input()
        if option.lower() == "yes":
            reply_ok = True
            sprint ("Lets go!!")
            player_name = ""
            total_points = 0
            cls()
        elif option.lower() == "no": 
            reply_ok = True
            play = False # stop our main loop
            sprint("I knew you weren't worthy anyway.\n")
        else:
            print ("\033[1;33mPlease choose an option.\033[0;37;40m (yes/no)\n")

def end_game():
    global play,total_points
    cls()
    sprint("""All of a sudden the Magick of your ancestors flood through your body, you feel supremely powerful.
    You gain the knowledge of an expert Magician. Now it is time to choose your destiny path.
    \033[1;33mDo you choose Path 1, Path 2 or Path 3?\033[0;37;40m\n""")
    sprint("""
    
    Please enter :       1             2              3   
    
    Choose carefully and wisely, as this decides your fate  
    
    """)
    is_choice_ok = False
    while is_choice_ok == False: # loop until we have a valid choice
        choice=input()
        if choice == "1":
            is_choice_ok = True
            total_points += 1000
            sprint("You chose the first path: You band together with the residents of the Kingdom, and with the help of your awesome Magick powers you overthrow the despot tyrant King. Peace and prosperity reigns in the land forevermore\n")
            sprint("\nCONGRATULATIONS, you escaped and realised your true destiny!!\n")
        elif choice == "2":
            is_choice_ok = True
            total_points += 500
            sprint("You chose the second path: You succumb to the awesome dark power of the ancient Magick and begin your reign of terror on the peoples of the land.\n")
            sprint("\nCONGRATULATIONS, you escaped!!.......but at what cost?\n")
        elif choice == "3":
            is_choice_ok = True
            total_points += 100
            sprint("You chose the third path : You manage to sneak out of the castle you were held captive in and smuggle yourself onto a ship bound for a new land. You fade into obscurity and are never heard from again.\n")
            sprint("\nCONGRATULATIONS, you escaped from the evil Kings clutches.\n")
        elif choice == "4":
            is_choice_ok = True
            total_points += 50
            sprint("\nYou defy all known logic, you refuse to conform to societal norms. You are basically Jesus, or like, the Dalai-Lama or some shit. Wow. I just have no words. Who even are you?\n")
        elif choice == "666":
            is_choice_ok = True
            total_points += 666
            sprint("\nYou summon the Devil and dance naked in the moonlight.\n")
        elif choice == "420":
            is_choice_ok = True
            total_points += 420
            sprint("\nDUDE, like, where are my cheetos?\n")
        else:
            total_points -= 50
            sprint("Try again.")    
    congratulations()

# end of story

# game engine
cls() # first clear the screen
print_welcome()
while play == True: # loop until play == False
    time_start = datetime.now()
    get_player_name()
    ready_to_play()
    first_pink()
