# Parity Game Solver

This project parses Extended HOA (eHOA) files, constructs parity games from automata descriptions, and solves them using Zielonka's algorithm. It processes all `.ehoa` files in a specified directory and saves the winning states for each player (Eve and Adam) in separate result files.

## Features

1. **Parsing eHOA Files**:
   - Extracts controllable atomic propositions (APs) and other automaton properties.
   - Focuses on *transition-based acceptance conditions*.

2. **Parity Game Construction**:
   - Maps automaton states and transitions into parity game nodes and edges.
   - Assigns ownership of states and priorities based on automaton properties.

3. **Zielonka's Algorithm**:
   - Recursively determines the winning states for Eve and Adam.
   - Implements the "max even" acceptance condition.

4. **File Handling**:
   - Processes all `.ehoa` files in a given directory.
   - Skips files with excessive acceptance sets to maintain scalability.

5. **Output**:
   - Saves results to `<filename>_winnings.txt` for each `.ehoa` file.

## How to Run

1. Place all `.ehoa` files in the directory `/content/parity/keiren/`.
2. Run the script in a Python environment with `spot` installed.
3. Outputs will be saved in the current working directory.

## File Structure

- `paritygames.ipynb` — Main notebook for parsing, solving, and saving results.
- `.ehoa` files — Input files containing automaton descriptions.
- `<filename>_winnings.txt` — Output files for each `.ehoa` processed.

## Example Output

For an input file `example.ehoa`, the output file `example.ehoa_winnings.txt` contains:
```plaintext
Adam Wins: [0, 2, 4]
Eve Wins: [1, 3, 5]