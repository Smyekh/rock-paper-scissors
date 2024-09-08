# Rock Paper Scissors Game

A simple implementation of the classic **Rock Paper Scissors** game using JavaScript. This game allows the player to compete against the computer.

## Table of Contents

1. [Features](#features)
2. [Technologies Used](#technologies-used)
3. [Installation](#installation)
4. [How to Play](#how-to-play)
5. [Code Overview](#code-overview)
6. [Contributing](#contributing)
7. [License](#license)

---

## Features

- **Interactive UI**: Users can select their move (rock, paper, or scissors) using buttons.
- **Random Computer Move**: The computer selects a random move.
- **Result Display**: The game displays whether the player won, lost, or tied after each round.
- **Responsive Design**: Works on both desktop and mobile devices.

## Technologies Used

- **HTML**: Markup structure for the interface.
- **CSS**: Styles for layout and appearance.
- **JavaScript**: Game logic, event handling, and interactivity.

## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Smyekh/rock-paper-scissors.git
   ```

2. **Navigate to the project directory**:
   ```bash
   cd rock-paper-scissors
   ```

3. **Open the index.html file in a browser** to play the game.

## How to Play

1. Select your move by clicking on the **Rock**, **Paper**, or **Scissors** button.
2. The computer will automatically choose its move.
3. The result (win, lose, or draw) will be displayed.
4. The game keeps track of your score against the computer.

## Code Overview

Here’s a brief breakdown of the files and logic:

- **index.html**: Contains the game interface with buttons for Rock, Paper, and Scissors.
- **style.css**: Provides basic styling for the game.
- **index.js**: Handles the game logic:
  - Generates a random move for the computer.
  - Compares the player’s move with the computer’s to determine the result.
  - Updates the score and displays the result in the UI.

### Example Code Snippet (from `index.js`):
```javascript
const playerText = document.querySelector("#playerText");
const computerText = document.querySelector("#computerText");
const resultText = document.querySelector("#resultText");

const choiceBtns = document.querySelectorAll(".choiceBtn")

let player;
let computer;
let result;

choiceBtns.forEach(button => button.addEventListener("click",() =>{
    player = button.textContent;
    computerTurn();
    playerText.textContent = `Player: ${player}`;
    computerText.textContent = `Computer: ${computer}`;
    resultText.textContent = checkWinner();
}))

function computerTurn(){
    const randNum = Math.floor(Math.random() * 3) + 1;

    switch(randNum){
        case 1:
            computer = "ROCK";
            break;
        case 2:
            computer = "PAPER";
            break;
        case 3:
            computer ="SCISSORS";
            break;
        
    }
}

function checkWinner(){
    if(player == computer){
        return "Draw!";
    }
    else if(computer == "ROCK"){
        return(player == "PAPER") ? "You Win!" : "You Lose!";
    }
    else if(computer == "PAPER"){
        return(player == "SCISSORS") ? "You Win!" : "You Lose!";
    }
    else if(computer == "SCISSORS"){
        return(player == "ROCK") ? "You Win!" : "You Lose!";
    }
}
```

## Contributing

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes.
4. Push the branch (`git push origin feature-branch`).
5. Open a Pull Request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
