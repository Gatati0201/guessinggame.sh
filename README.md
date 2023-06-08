# guessinggame.sh

#!/bin/bash

function guessing_game {
  local correct_guess=false
  local file_count=$(ls -l | grep "^-" | wc -l)

  while [[ $correct_guess == false ]]
  do
    echo "Combien de fichiers se trouvent dans le répertoire courant ?"
    read guess

    if [[ $guess -lt $file_count ]]
    then
      echo "Trop bas ! Essayez encore."
    elif [[ $guess -gt $file_count ]]
    then
      echo "Trop haut ! Essayez encore."
    else
      echo "Félicitations ! Vous avez deviné le bon nombre de fichiers."
      correct_guess=true
    fi
  done
}

guessing_game
