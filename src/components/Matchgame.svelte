<script>
    let initialCards = [
    { id: 1, pair: "1", value: "🫀", matched: false },
    { id: 2, pair: "2", value: "🦠", matched: false },
    { id: 3, pair: "3", value: "🔭", matched: false },
    { id: 4, pair: "4", value: "🔬", matched: false },
    { id: 5, pair: "5", value: "🧪", matched: false },
    { id: 6, pair: "6", value: "🧬", matched: false },
    { id: 7, pair: "7", value: "🧠", matched: false },
    { id: 8, pair: "8", value: "🥼", matched: false },

    { id: 9, pair: "1", value: "🫀", matched: false },
    { id: 10, pair: "2", value: "🦠", matched: false },
    { id: 11, pair: "3", value: "🔭", matched: false },
    { id: 12, pair: "4", value: "🔬", matched: false },
    { id: 13, pair: "5", value: "🧪", matched: false },
    { id: 14, pair: "6", value: "🧬", matched: false },
    { id: 15, pair: "7", value: "🧠", matched: false },
    { id: 16, pair: "8", value: "🥼", matched: false },
  ];

  let cards = [];
  let selected = [];
  let moves = 0;
  let timer = 0;
  let interval;
  let gameStarted = false;

  function shuffle(array) {
    return array.sort(() => Math.random() - 0.5);
  }

  function resetGame() {
    cards = shuffle([...initialCards.map(card => ({ ...card }))]); // Reset and shuffle
    selected = [];
    moves = 0;
    timer = 0;
    gameStarted = false;

    if (interval) clearInterval(interval);
  }

  function startTimer() {
    if (!gameStarted) {
      gameStarted = true;
      interval = setInterval(() => {
        timer += 1;
      }, 1000);
    }
  }


  function selectCard(card) {
    if (!gameStarted) startTimer(); // Start timer on first move
    if (selected.length < 2 && !selected.includes(card) && !card.matched) {
      selected = [...selected, card];
    }

    if (selected.length === 2) {
      moves++;
      if (selected[0].pair === selected[1].pair) {
        selected[0].matched = true;
        selected[1].matched = true;
      }
      setTimeout(() => (selected = []), 1000);
    }
    if (cards.every(card => card.matched)) {
      clearInterval(interval); // Stop timer when all matches are found
    }
  }
  resetGame(); // Initialize the game on load
  
</script>

<div class="flex flex-col items-center justify-center h-screen bg-gray-900 text-white">
    <h1 class="text-3xl font-bold mb-4">Match Game</h1>
    <p class="mb-4">Moves: {moves}</p>
    <p class="mb-4">Time: {timer} sec</p>
    
    <div class="grid grid-cols-4 gap-4">
      {#each cards as card}
        <button
          class="w-16 h-16 flex items-center justify-center text-5xl bg-gray-700 rounded-lg shadow-md transition-transform"
          on:click={() => selectCard(card)}
          class:selected={selected.includes(card) || card.matched}
        >
          {#if selected.includes(card) || card.matched}
            {card.value}
          {:else}
            ❓
          {/if}
        </button>
      {/each}
    </div>
    <button on:click={resetGame} class="mt-6 px-4 py-2 bg-blue-500 hover:bg-blue-700 text-white font-bold rounded">
        Reset Game
    </button>
  </div>

  <style>
    .selected {
      background-color: #38bdf8;
    }
  </style>
