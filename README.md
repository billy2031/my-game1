# my-game1 (Unfinsihed)
@echo off
color 7c
title Chaos Dawn
echo Welcome to Chaos Dawn!
echo.

:main
cls
echo Welcome to Chaos Dawn Character Creator!
echo -----------------------------------------
echo.
echo Select your character's race:
echo 1. Human
echo 2. Elf
echo 3. Dwarf
echo 4. Orc
echo 5. Goblin
echo 6. Troll
echo 7. Dragonborn
echo 8. Tiefling
echo 9. Halfling
echo 10. Gnome
echo 11. Vampire
echo 12. Werewolf
echo 13. Centaur
echo 14. Minotaur
echo 15. Fairy
echo 16. Angel
echo 17. Demon
echo 18. Mermaid
echo 19. Satyr
echo 20. Giant
echo.
set /p race=Enter the number of your chosen race (1-20): 

if %race%==1 set race_name=Human
if %race%==2 set race_name=Elf
if %race%==3 set race_name=Dwarf
if %race%==4 set race_name=Orc
if %race%==5 set race_name=Goblin
if %race%==6 set race_name=Troll
if %race%==7 set race_name=Dragonborn
if %race%==8 set race_name=Tiefling
if %race%==9 set race_name=Halfling
if %race%==10 set race_name=Gnome
if %race%==11 set race_name=Vampire
if %race%==12 set race_name=Werewolf
if %race%==13 set race_name=Centaur
if %race%==14 set race_name=Minotaur
if %race%==15 set race_name=Fairy
if %race%==16 set race_name=Angel
if %race%==17 set race_name=Demon
if %race%==18 set race_name=Mermaid
if %race%==19 set race_name=Satyr
if %race%==20 set race_name=Giant

if not defined race_name (
    echo Invalid selection. Please choose a number between 1 and 20.
    pause
    goto main
)

cls
echo you have chosen: %race_name%
echo.
set /p name=Enter your character's name: 
cls
echo -----------------------------------------
echo Your character has been created!
echo Name: %name%
echo Race: %race_name%
echo -----------------------------------------
goto prologe

:Prologe
You find yourself in a dark room with three doors.
echo.
goto main

:main
echo Choose a door to open:
echo 1. Door on the left
echo 2. Door in the center
echo 3. Door on the right
echo 4. Do nothing
echo 5. rick
set /p choice="Your choice (left, center, right, nothing, rick): "

if "%choice%"=="left" goto left
if "%choice%"=="center" goto center
if "%choice%"=="right" goto right
if "%choice%"=="nothing" goto nothing
if "%choice%"=="rick" goto rick
echo Invalid choice. Try again.
goto main

:rick
echo wait a couple seconds
curl ascii.live/rick

:left
echo You opened the left door and found a treasure chest!
goto escape

:right
echo You opened the right door and encountered a monster!
echo Battle
set player_name=Player
set /a player_hp=50
set /a player_atk=20

set ai_name=Monster
set /a ai_hp=50
set /a ai_atk=20

:game_loop
cls
echo %player_name% HP:100 %player_hp%
echo %ai_name% HP:100 %ai_hp%
echo -----------------------------------------

:: Player's Attack
echo %player_name% attacks %ai_name%!
set /a ai_hp=ai_hp-player_atk
if %ai_hp% LEQ 0 goto victory_player

:: AI's Attack
echo %ai_name% attacks %player_name%!
set /a player_hp=player_hp-ai_atk
if %player_hp% LEQ 0 goto victory_ai

pause
goto game_loop

:victory_player
cls
echo Congratulations, %player_name%! You have defeated the Monster!
goto escape

:victory_ai
cls
echo %ai_name% has defeated you. Better luck next time!
pause
exit

:center
echo You opened the center door and encountered a monster!
echo Battle
set player_name=Player
set /a player_hp=50
set /a player_atk=20

set ai_name=AI
set /a ai_hp=50
set /a ai_atk=20

:game_loop
cls
echo %player_name% HP:100 %player_hp%
echo %ai_name% HP:100 %ai_hp%
echo -----------------------------------------

:: Player's Attack
echo %player_name% attacks %ai_name%!
set /a ai_hp=ai_hp-player_atk
if %ai_hp% LEQ 0 goto victory_player

:: AI's Attack
echo %ai_name% attacks %player_name%!
set /a player_hp=player_hp-ai_atk
if %player_hp% LEQ 0 goto victory_ai

pause
goto game_loop

:victory_player
cls
echo Congratulations, %player_name%! You have defeated the Monster!
goto escape

:victory_ai
cls
echo %ai_name% has defeated you. Better luck next time!
pause
exit

:nothing
echo You wait and do nothing.
goto main

:escape
echo You have found the exit out of the cave.
echo What shall you do?
echo 1. Go Forward 
echo 2. Go Left 
echo 3. Go Right 

set /p choice="Your choice (1, 2, 3): "
if "%choice%"=="1" goto forward
if "%choice%"=="2" goto left_turn
if "%choice%"=="3" goto right_turn

:left_turn
echo You find a town.
echo What shall you do?
echo 1. Go to town
echo 2. Go Back 

set /p choice="Your choice (1, 2): "
if "%choice%"=="1" goto town
if "%choice%"=="2" goto gone_back

:right_turn
echo You find a forest.
echo What shall you do?
echo 1. Go to forest
echo 2. Go Back 

set /p choice="Your choice (1, 2): "
if "%choice%"=="1" goto forest
if "%choice%"=="2" goto go_back

:forest
echo you enter the forest 
echo you see the shadow infront of you
echo You opened the right door and encountered a monster!
echo Battle
set player_name=Player
set /a player_hp=50
set /a player_atk=20

set ai_name=???
set /a ai_hp=50
set /a ai_atk=20

:game_loop
cls
echo %player_name% HP:100 %player_hp%
echo %ai_name% HP:100 %ai_hp%
echo -----------------------------------------

:: Player's Attack
echo %player_name% attacks %ai_name%!
set /a ai_hp=ai_hp-player_atk
if %ai_hp% LEQ 0 goto victory_player

:: AI's Attack
echo %ai_name% attacks %player_name%!
set /a player_hp=player_hp-ai_atk
if %player_hp% LEQ 0 goto victory_ai

pause
goto game_loop

:victory_player
cls
echo Congratulations, %player_name%! You have defeated ???!
goto escape

:victory_ai
cls
echo %ai_name% has defeated you. Better luck next time!
pause
exit

:forward
echo You find a river in the way.
echo What shall you do?
echo 1. Try to go through the river
echo 2. Go back
echo 3. Give up

set /p choice="Your choice (1, 2, 3): "
if "%choice%"=="1" goto river
if "%choice%"=="2" goto escape
if "%choice%"=="3" goto end

:river
echo Oh no, %name%! You drowned. You failed!
goto end

:gone_back
echo Where do you go?
echo 1. Go to forest
echo 2. Go to town
echo 3. Go to river

set /p choice="Your choice (1, 2, 3): "
if "%choice%"=="1" goto forest
if "%choice%"=="2" goto town
if "%choice%"=="3" goto forward

:go_back
echo Where do you go?
echo 1. Go to forest
echo 2. Go to town
echo 3. Go to river

set /p choice="Your choice (1, 2, 3): "
if "%choice%"=="1" goto forest
if "%choice%"=="2" goto town
if "%choice%"=="3" goto forward

:town
echo You have found a busy and bustling town center.
echo Where do you go?
echo 1. Go to store


set /p choice="Your choice (1): "
if "%choice%"=="1" goto store

:store
echo you enter the store
echo you see a health bottle
echo what do you do now
echo 1. buy bottle 
echo 2. Rob at swordpoint

set /p choice="Your choice (1, 2): "
if "%choice%"=="1" goto Buy_bottle
if "%choice%"=="2" goto rob

:Buy_bottle
echo You brought the health bottle
echo You leave the store
goto good

color 7c
title bad path

:rob
echo You take out your sword
echo What do you do now?
echo 1. Kill the owner
echo 2. leave


set /p choice="Your choice (1, 2): "
if "%choice%"=="1" goto murder
if "%choice%"=="2" goto alt_town


:alt_town
echo you exit the store without trouble
echo you hear the police searching for you for attempted murder and thivery
echo What do you do?
echo 1. Go back and kill the owner
echo 2. Surrender
echo 3. Hide

if "%choice%"=="1" goto Fight_owner
if "%choice%"=="2" goto jail
if "%choice%"=="3" goto town

:murder
echo Battle
set player_name=Player
set /a player_hp=50
set /a player_atk=20

set ai_name=Owner
set /a ai_hp=50
set /a ai_atk=20

:game_loop
cls
echo %player_name% HP:100 %player_hp%
echo %ai_name% HP:100 %ai_hp%
echo -----------------------------------------

:: Player's Attack
echo %player_name% attacks %ai_name%!
set /a ai_hp=ai_hp-player_atk
if %ai_hp% LEQ 0 goto victory_player

:: AI's Attack
echo %ai_name% attacks %player_name%!
set /a player_hp=player_hp-ai_atk
if %player_hp% LEQ 0 goto victory_ai

pause
goto game_loop

:victory_player
cls
echo Congratulations, %player_name%! You are a murder..
goto Kill_owner

:victory_ai
cls
echo %ai_name% has defeated you. Better luck next time!
pause
exit


:Fight_owner
echo Battle
set player_name=Player
set /a player_hp=50
set /a player_atk=20

set ai_name=Owner
set /a ai_hp=50
set /a ai_atk=20

:game_loop
cls
echo %player_name% HP:100 %player_hp%
echo %ai_name% HP:100 %ai_hp%
echo -----------------------------------------

:: Player's Attack
echo %player_name% attacks %ai_name%!
set /a ai_hp=ai_hp-player_atk
if %ai_hp% LEQ 0 goto victory_player

:: AI's Attack
echo %ai_name% attacks %player_name%!
set /a player_hp=player_hp-ai_atk
if %player_hp% LEQ 0 goto victory_ai

pause
goto game_loop

:victory_player
cls
echo Congratulations, %player_name%! You are a murder..
goto Kill_owner

:victory_ai
cls
echo %ai_name% has defeated you. Better luck next time!
pause
exit

:Kill_owner
echo You stab the owner in the neck
echo you hear the police outside
echo the police attack you and you go to jail
goto prison

:prison
echo you are in jail!
echo what will you do?
echo 1. Escape
echo 2. Stay

if "%choice%"=="1" goto leave_town
if "%choice%"=="2" goto Stay

:Stay
echo You decided to stay at the jail
echo You go to court the next day, %name%! You get 21 Years for attempted Murder. You failed!
goto end

:Escape
echo you escaped the police force
echo they dont know it is you who commited the crime
goto kill_town

:kill_town
echo you must leave the town
Goto end

:end 
pause
exit
