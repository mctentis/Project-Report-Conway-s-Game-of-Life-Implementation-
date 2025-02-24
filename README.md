# Project-Report-Conway-s-Game-of-Life-Implementation-
This project involved creating a simple implementation of Conway’s Game of Life using Test-Driven Development (TDD). The goal was to build a JavaScript function that applies the rules of the game to determine the next state of a cell based on its current state and the number of live neighbors. 
unction Code: 

javascript 

function getNextCellState(currentState, liveNeighbors) { 
  if (currentState === "Live") { 
    if (liveNeighbors < 2 || liveNeighbors > 3) { 
      return "Dead"; // Rule 1 and Rule 2 
    } else { 
      return "Live"; // Rule 3 
    } 
  } else { 
    if (liveNeighbors === 3) { 
      return "Live"; // Rule 4 
    } else { 
      return "Dead"; 
    } 
  } 
} 

 

3. Writing Unit Tests 

Unit tests were written using Jest to ensure the function behaves as expected. The tests cover all four rules of the game. 

Test Code: 

javascript 

const { getNextCellState } = require("./gameOfLife"); 
 
test("Live cell with fewer than 2 live neighbors dies", () => { 
  expect(getNextCellState("Live", 1)).toBe("Dead"); // Rule 1 
}); 
 
test("Live cell with 2 or 3 live neighbors lives", () => { 
  expect(getNextCellState("Live", 2)).toBe("Live"); // Rule 3 
  expect(getNextCellState("Live", 3)).toBe("Live"); // Rule 3 
}); 
 
test("Live cell with more than 3 live neighbors dies", () => { 
  expect(getNextCellState("Live", 4)).toBe("Dead"); // Rule 2 
}); 
 
test("Dead cell with exactly 3 live neighbors becomes alive", () => { 
  expect(getNextCellState("Dead", 3)).toBe("Live"); // Rule 4 
}); 

 

4. Running the Tests 

The tests were run using the following command: 

bash 

Copy 

npm test 
