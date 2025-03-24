<script>
  import { onMount } from "svelte";

  let words = ["svelte", "tailwind", "javascript", "frontend", "developer"];
  let secretWord = "";
  let guessedLetters = new Set();
  let wrongGuesses = 0;
  let maxWrongGuesses = 6;
  let gameOver = false;
  let gameWon = false;
  let displayWord = ""; //added this show correct guesses of letters in secret word and display it in a seperate section.

  function chooseRandomWord() {
    secretWord = words[Math.floor(Math.random() * words.length)].toUpperCase();
    guessedLetters.clear();
    updateDisplayWord();
  }

  function guessLetter(letter) {
    if (gameOver || gameWon || guessedLetters.has(letter)) return;

    guessedLetters.add(letter);

    if (!secretWord.includes(letter)) {
      wrongGuesses++;
    }

    updateDisplayWord();
    checkGameStatus();
  }

// Add this function to update blanks when correct letters chosen then call it in guessletter function AND in choose random word function
  function updateDisplayWord() {
    displayWord = secretWord
      .split("")
      .map(letter => (guessedLetters.has(letter) ? letter : "_"))
      .join(" ");
  }

  //displayword used in function below to update gamestatus by checking if there are any blanks in displayword
  function checkGameStatus() {
    if (!displayWord.includes("_")) {
      gameWon = true;
    }

    if (wrongGuesses >= maxWrongGuesses) {
      gameOver = true;
    }
  }

  function resetGame() {
    guessedLetters.clear();
    wrongGuesses = 0;
    gameOver = false;
    gameWon = false;
    chooseRandomWord();
  }

  onMount(() => {
    chooseRandomWord();
  });
</script>

<main class="flex flex-col items-center justify-center min-h-screen bg-gray-900 text-white">
  <h1 class="text-3xl font-bold mb-4">Word Guessing Game</h1>
  <p class="text-lg mb-4">Guess the word letter by letter!</p>

  <!-- Display Word with Spaces -->
  <div class="text-3xl font-mono tracking-wide mb-6">
    {displayWord}
  </div>

  <!-- Wrong Guess Count -->
  <p class="text-red-400 mb-4">Wrong Guesses: {wrongGuesses} / {maxWrongGuesses}</p>

  <!-- Game Result Messages -->
  {#if gameWon}
    <p class="text-green-400 text-xl font-bold mb-4">🎉 You Won! 🎉</p>
  {:else if gameOver}
    <p class="text-red-400 text-xl font-bold mb-4">😢 You Lost! The word was "{secretWord}"</p>
  {/if}

  <!-- Letter Buttons -->
  <div class="grid grid-cols-9 gap-2 mb-6">
    {#each "ABCDEFGHIJKLMNOPQRSTUVWXYZ".split("") as letter}
      <button
        on:click={() => guessLetter(letter)}
        disabled={guessedLetters.has(letter)}
        class="w-10 h-10 bg-gray-700 hover:bg-blue-500 text-white font-bold rounded disabled:opacity-50"
      >
        {letter}
      </button>
    {/each}
  </div>

  <!-- Restart Button -->
  <button
    on:click={resetGame}
    class="px-4 py-2 bg-blue-500 hover:bg-blue-700 text-white font-bold rounded"
  >
    Restart Game
  </button>
</main>


  