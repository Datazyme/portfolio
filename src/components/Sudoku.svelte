<script>
    import { onMount } from "svelte";
  
    // Example Sudoku board (0 represents empty spaces)
    const initialBoard = [
      [5, 3, 0, 0, 7, 0, 0, 0, 0],
      [6, 0, 0, 1, 9, 5, 0, 0, 0],
      [0, 9, 8, 0, 0, 0, 0, 6, 0],
      [8, 0, 0, 0, 6, 0, 0, 0, 3],
      [4, 0, 0, 8, 0, 3, 0, 0, 1],
      [7, 0, 0, 0, 2, 0, 0, 0, 6],
      [0, 6, 0, 0, 0, 0, 2, 8, 0],
      [0, 0, 0, 4, 1, 9, 0, 0, 5],
      [0, 0, 0, 0, 8, 0, 0, 7, 9]
    ];
  
    let board = JSON.parse(JSON.stringify(initialBoard)); // Make a deep copy
    let selectedCell = { row: null, col: null };
    let message = ""; // Message to display validation errors
    
    //Selects a cell in the Sudoku grid so the user can input a number. 
    //Updates the selectedCell variable with the row and column index of the clicked cell.
    // This allows the game to track which cell is active.
    // When a cell is selected, it changes color (bg-blue-500) in the UI.
    function selectCell(row, col) {
      selectedCell = { row, col };
      message = ""; // Clear message when selecting a new cell
    }
    
    //Allows the user to input a number into the selected cell, but only if it's empty.
    //First, it checks if a cell is selected (selectedCell.row !== null).
    //Then, it ensures the cell is empty before allowing input (board[selectedCell.row][selectedCell.col] === 0).
    //If valid, it updates the board with the user's chosen number.
    //After input, it deselects the cell (selectedCell = { row: null, col: null }).
    function enterNumber(num) {
        if (selectedCell.row !== null && board[selectedCell.row][selectedCell.col] === 0) {
            if (isValidMove(selectedCell.row, selectedCell.col, num)) {
                board[selectedCell.row][selectedCell.col] = num;
                selectedCell = { row: null, col: null }; // Deselect cell after input
                message = ""; // Clear any previous error message
            } else {
            message = `❌ ${num} is not allowed in this position!`;
        }
        }
    }


    function isValidMove(row, col, num) {
        // Check if the number exists in the same row
        if (board[row].includes(num)) return false;

        // Check if the number exists in the same column
        for (let i = 0; i < 9; i++) {
        if (board[i][col] === num) return false;
        }

        // Check if the number exists in the 3x3 grid
        const startRow = Math.floor(row / 3) * 3;
        const startCol = Math.floor(col / 3) * 3;
        for (let i = 0; i < 3; i++) {
        for (let j = 0; j < 3; j++) {
            if (board[startRow + i][startCol + j] === num) return false;
        }
        }

        return true; // Move is valid
    }
  
    //Resets the board to its original state by making a fresh copy of the initial puzzle.
    //Deep copies initialBoard using JSON.parse(JSON.stringify(initialBoard)) so that the reset is complete.
    //Prevents modifying the original board, ensuring that every reset starts from scratch.
    //Deselects any selected cell (selectedCell = { row: null, col: null }).
    function resetGame() {
      board = JSON.parse(JSON.stringify(initialBoard)); // Reset to original state
      selectedCell = { row: null, col: null };
      message = "";
    }
  </script>
  
  <main class="flex flex-col items-center justify-center bg-gray-900 text-white pt-6 pl-4 pr-4">
    <h1 class="text-3xl font-bold mb-4">Sudoku Game</h1>
  
    <!-- Sudoku Grid -->
    <div class="grid grid-cols-9 gap-1 p-2 border-4 border-gray-500">
      {#each board as row, rowIndex}
        {#each row as cell, colIndex}
          <button
            class="w-10 h-10 flex items-center justify-center text-xl font-bold border border-gray-400
                   {selectedCell.row === rowIndex && selectedCell.col === colIndex ? 'bg-blue-500' : 'bg-gray-700'}"
            on:click={() => selectCell(rowIndex, colIndex)}
          >
            {cell !== 0 ? cell : ""}
          </button>
        {/each}
      {/each}
    </div>

    <!-- Error Message -->
    {#if message}
        <p class="mt-4 text-red-400 font-bold">{message}</p>
    {/if}
  
    <!-- Number Buttons -->
    <div class="grid grid-cols-9 gap-2 mt-4">
      {#each Array(9).fill(0).map((_, i) => i + 1) as num}
        <button
          class="w-10 h-10 bg-blue-500 hover:bg-blue-700 text-white font-bold rounded"
          on:click={() => enterNumber(num)}
        >
          {num}
        </button>
      {/each}
    </div>
  
    <!-- Reset Button -->
    <button
      on:click={resetGame}
      class="mt-4 px-4 py-2 bg-blue-500 hover:bg-red-700 text-white font-bold rounded"
    >
      Reset Game
    </button>
  </main>
  
  