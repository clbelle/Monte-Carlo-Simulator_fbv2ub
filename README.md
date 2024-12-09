# Monte-Carlo-Simulator_fbv2ub
Monte Carlo simulator created for DS5100 final project

Monte Carlo Simulator
This project implements a Monte Carlo simulator using three interrelated classes: DieClass, Game, and Analyzer. These classes allow for the simulation, analysis, and visualization of random events such as rolling dice with weighted outcomes.

Overview
Classes

DieClass:

Models a die with customizable faces and weights.
Provides methods to roll the die and view its configuration.
Represents the fundamental unit for simulation.

Game:

Simulates rolling one or more dice.
Organizes roll outcomes into data structures for analysis.
Allows for customization of the output format.

Analyzer:

Analyzes the outcomes of a game.
Provides insights such as jackpots, face counts, and frequency of combinations or permutations.

Install dependencies:
bash
Copy code
pip install numpy pandas

Usage
1. DieClass
Initialize a die
python
Copy code
import numpy as np
from simulator import DieClass

sides = np.array([1, 2, 3, 4, 5, 6])
die = DieClass(sides)
Modify a die's weight
python
Copy code
die.set_weight(3, 2.5)  # Sets the weight of face 3 to 2.5
Roll the die
python
Copy code
outcomes = die.roll(num_rolls=10)
View die configuration
python
Copy code
die.show()
2. Game
Initialize a game with multiple dice
python
Copy code
from simulator import Game

dice = [DieClass(np.array([1, 2, 3, 4, 5, 6])) for _ in range(2)]  # Create two dice
game = Game(dice)
Play the game
python
Copy code
game.play(num_rolls=5)  # Rolls the dice 5 times
Show game results
python
Copy code
results_wide = game.show(form="wide")
results_narrow = game.show(form="narrow")
3. Analyzer
Analyze game results
python
Copy code
from simulator import Analyzer

analyzer = Analyzer(game)
Calculate jackpots
python
Copy code
jackpot_count = analyzer.jackpot()
Count faces per roll
python
Copy code
face_counts = analyzer.face_counts_per_roll()
Compute combination frequencies
python
Copy code
combo_counts = analyzer.combo_count()
Compute permutation frequencies
python
Copy code
permutation_counts = analyzer.permutation_count()
Examples
python
Copy code
# Example: Simulate a weighted die roll and analyze results
die = DieClass(np.array(['A', 'B', 'C']))
die.set_weight('A', 2)  # Increase the weight for 'A'

game = Game([die])
game.play(num_rolls=10)

analyzer = Analyzer(game)
print("Jackpots:", analyzer.jackpot())
print("Face Counts:\n", analyzer.face_counts_per_roll())
print("Combination Counts:\n", analyzer.combo_count())
Features
Customizable Dice: Supports weighted outcomes for dice rolls.
Multiple Dice Simulation: Play games with one or more dice.
Comprehensive Analysis: Includes jackpots, face counts, combinations, and permutations.
Flexible Data Formats: Provides results in wide or narrow formats for easy interpretation.
License
This project is licensed under the MIT License.

Contributing
Contributions are welcome! Please follow these steps:

Fork the repository.
Create a feature branch:
bash
Copy code
git checkout -b feature-name
Commit your changes:
bash
Copy code
git commit -m "Add feature-name"
Push to your fork:
bash
Copy code
git push origin feature-name
Open a pull request.
Contact
For questions or feedback, please contact C. Belle.
