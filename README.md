#!/bin/bash

function GetNumFiles {
	echo $(ls -la | grep "^-" | wc -l)
}

function PrintRules {
	  echo "We are trying to guess how many files in the current directory."echo "After the message \"Type in your number:\", please enter your your number and press Enter."
	      echo "We will play the game forever till you guess the right answer."
	   echo "Let's start our game. Good luck!"
	     echo
}
	
function Game {
	    right_num_files=$(GetNumFiles)
	    while true
	do
		echo -n "Type in your number: "
		read num_files
        	if [[ $num_files -eq $right_num_files ]]
		then
			echo "Great! You guess the right number of files in the current directory!"
			exit 0
		elif [[ $num_files -lt $right_num_files ]]
		then
			echo "Your number is lower than number of files in the current directory! Please, try again."
		else
			echo "Your number is upper then number of files in the current directory! Please, try again."
        	fi
	   done
}

PrintRules
Game


