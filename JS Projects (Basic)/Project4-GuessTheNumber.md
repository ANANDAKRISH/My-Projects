# Project 4- GuessTheNumber
### Project Link : [Click Here](https://stackblitz.com/edit/stackblitz-starters-drvbqn?file=Project%201%20-%20ColorChanger%2Fscript.js)

## Problem : 
A random number is generated between 1 & 100. The user needs to guess the number within his allotted 10 turns . The user looses once all the turns are exhausted and wins if he guesses it correctly within his 10 turns. The user must be guided to the correct direction by giving him the hint on whether the guessed number is lower or higher than the actual number. After the game ends , the user must be given an option to start a new game.

## Solution Code:
```javascript
let randomNumber = parseInt(Math.random() * 100 + 1);

const input = document.querySelector('#guessField');
const submit = document.querySelector('#subt');
const prevGuesses = document.querySelector('.guesses');
const remGuesses = document.querySelector('.lastResult');
const lowOrHigh = document.querySelector('.lowOrHi');
const resultParas = document.querySelector('.resultParas');

const p = document.createElement('p');
let currGuess = 0;
let playGame = true;

submit.addEventListener('click', function (e) {
  e.preventDefault();
  if (playGame) {
    const guessedNumber = parseInt(input.value);
    inputValidation(guessedNumber);
  }
});

function inputValidation(inp) {
  if (isNaN(inp)) {
    alert('The entered input is not valid');
    input.value = '';
  } else if (inp < 1) {
    alert(`The entered input ${inp} is less than 1.Enter a number > 1`);
    input.value = '';
  } else if (inp > 100) {
    alert(`The entered input ${inp} is greater than 100. Enter a number < 100`);
    input.value = '';
  } else {
    guessCheck(inp);
  }
}

function guessCheck(inp) {
  currGuess++;
  if (currGuess === 10) {
    prevGuesses.innerHTML += `${inp}`;
    remGuesses.innerHTML = `${10 - currGuess}`;
    if (inp === randomNumber) {
      displayMessage('Congragulations!! You have Won the Game');
    } else {
      displayMessage(
        `All the turns have been exhausted. The actual number is ${randomNumber}`
      );
    }
    endGame();
  } else if (inp === randomNumber) {
    displayMessage('Congragulations!! You have Won the Game');
    endGame();
  } else {
    input.value = '';
    prevGuesses.innerHTML += `${inp},`;
    remGuesses.innerHTML = `${10 - currGuess}`;
    if (inp > randomNumber) {
      displayMessage('Guessed number is higher than actual number');
    } else {
      displayMessage('Guessed number is lower than actual number');
    }
  }
}

function displayMessage(message) {
  lowOrHigh.innerHTML = `<h2>${message}</h2>`;
}

function endGame() {
  playGame = false;
  input.value = '';
  input.setAttribute('disabled', '');
  p.classList.add('button');
  p.innerHTML = '<h2 id="newgame">START NEWGAME</h2>';
  resultParas.appendChild(p);
  newGame();
}

function newGame() {
  const nextgame = document.querySelector('#newgame');
  nextgame.addEventListener('click', function (e) {
    input.removeAttribute('disabled');
    input.value = '';
    currGuess = 0;
    prevGuesses.innerHTML = '';
    remGuesses.innerHTML = `${10 - currGuess}`;
    lowOrHigh.innerHTML = '';
    randomNumber = parseInt(Math.random() * 100 + 1);
    resultParas.removeChild(p);
    playGame = true;
  });
}

```