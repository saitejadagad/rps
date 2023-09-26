# rps
<!DOCTYPE html>
<html>
<head>
    <title>RPS GAME</title>
</head>
<body>
    <h2>Rock, Paper, and Scissor</h2>
    <p>Choose your choice rock,paper or scissor</p>
    <input type="text" id="fgame" placeholder="Enter your choice">
    <button onclick="Game()">Play</button>
    <p id="result"></p>

    <script>
        function Game() {
            const choices = ["rock", "paper", "scissor"];
            const userInput = document.getElementById('fgame');
            const resultDisplay = document.getElementById('result');
            
            let pChoice = userInput.value.toLowerCase();// converting input to lowercase

            try {
                if (!choices.includes(pChoice)) {
                    throw new Error("Invalid choice. Please choose rock, paper, or scissors.");
                }/* if user gives any input other than rock,paper or scissor than it throw a
                 user friendly message*/

                const compChoice = choices[Math.floor(Math.random() * choices.length)];/* converting 
             
            array indexes random outcomes by using Math.random method()*/

                if (pChoice === compChoice) {
                    resultDisplay.textContent = "It's a tie!"; // both chooses same than its tie
                } else if (
                    (pChoice === "rock" && compChoice === "scissor") ||
                    (pChoice === "paper" && compChoice === "rock") ||
                    (pChoice === "scissors" && compChoice === "paper")
                ) {
                    resultDisplay.textContent = `You win! Computer chose ${compChoice}.`;
                } else {
                    resultDisplay.textContent = `Computer wins! Computer chose ${compChoice}.`;
                }
            } catch (error) {
                resultDisplay.textContent = error.message;
            }
        }
    </script>
</body>
</html>
