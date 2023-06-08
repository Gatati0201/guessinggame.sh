# guessinggame.sh

#!/bin/bash

# Fonction pour obtenir le nombre de fichiers dans le répertoire courant
function get_file_count {
  local count=$(ls -l | grep "^-" | wc -l)
  echo "$count"
}

# Boucle principale du jeu de devinettes
function guessing_game {
  local file_count=$(get_file_count)
  local guess=0

  while [[ $guess -ne $file_count ]]
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
    fi
  done
}

guessing_game


