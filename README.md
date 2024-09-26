

Group member: Chuanrun Zhang, Qing Lyu

This is the Assignment 2: Automated Puzzle Solving

This assignment investigates a class of puzzles that have the following features in common:

feature description full information all information about the puzzle state at any given point is visible to the solver; there are no hidden or random aspects well-defined extensions a definition of legal "extensions" from a given puzzle state to new states is given well-defined solution a definition of what it means for the puzzle to be in a solved state is given These features are common to a very large class of puzzles: crosswords, sudoku, peg solitaire, verbal arithmetic, and so on. This assignment generalizes the required features into an abstract superclass Puzzle and solving such puzzles is written in terms of this abstract class.

Once this is done, particular concrete puzzles can be modelled as subclasses of Puzzle and solved using the solve method of a subclass of the Solver abstract class, which will be described later.

Although there may be faster puzzle-specific solvers for a particular puzzle that take advantage of specific features of that puzzle, the general solvers you will build are designed to work for all puzzles of this sort.

There are there main puzzles:

Sudoku This puzzle commonly appears in print media and online. You are presented with an n × n grid with some symbols, for example digits or letters, filled in. The symbols must be from a set of n symbols. The goal is to fill in the remaining symbols in such a way that each row, column, and subsquare, contains each symbol exactly once. In order for all of that to make sense, n must be a square integer such as 4, 9, 16, or 25.

You may want to read more about sudoku (Links to an external site.) to get a feel for the puzzle if you aren’t already familiar with it.

Word Ladder This puzzle involves transforming one word into a target word by changing one letter at a time. Each word must belong to a specified set of valid words. Here’s an example where we assume that the set of valid words is a rather large set of common English words, and the goal is to get from the word ‘cost’ to the word ‘save’:

cost → cast → case → cave → save

Expression Tree Puzzle This puzzle consists of an algebraic equation containing one or more variables, and a target value. The puzzle is solved when the variables are assigned values such that the expression evaluates to the target value.

The search algorithms:

Depth-first search and breadth-first search are two approaches to searching through the space of possibilities for a solution.

With depth-first search, we search deeply before we search broadly. We exhaustively search the first subtree before considering any other subtree. And we use the same strategy when we search that subtree: exhaustively searching its first subtree before considering any other subtree. And so on - think recursively!

With breadth-first search, we search broadly before we search deeply. We consider all puzzle states at depth 1, then all puzzle states at depth 2, and so on until we have searched all puzzle states in our tree. (You will find a queue is helpful for keeping track of puzzles states to be checked when their turn comes.) Because we consider states that are “closer” to the starting state before those that are “farther”, we are guaranteed to find the shortest path to a puzzle’s solution.

For both solvers, we run the risk of encountering a puzzle state that we've already seen, and which already failed to produce a solution. To avoid exploring that state all over again, we will keep track of states we've seen before and just ignore them if we encounter them again.

For certain puzzle types, we might also be able to check whether we can quickly tell if a puzzle state is unsolvable. Such a check can be incorporated into our search algorithms and you will do so in your implementation.

Learning goals:

read complex code you didn’t write and understand its design and implementation, including: reading the class and method docstrings carefully (including attributes, representation invariants, preconditions, etc.) understanding relationships between classes, by applying your knowledge of composition and inheritance complete a partial implementation of a class, including: reading the representation invariants to enforce important facts about implementation decisions reading the preconditions to factor in assumptions that they permit writing the required methods according to their docstrings use inheritance to define a subclass of an abstract parent class implementing algorithms by translating their steps into python code by: choosing an appropriate ADT to solve the problem deciding if recursion is appropriate implement recursive methods for trees when provided with their specifications. perform unit testing on a program to verify correctness

And more specifically:

implement depth and breadth first searches to solve logic puzzles implement a simple expression tree class be able to implement additional logic puzzles beyond those in this assignment explore the behaviour of depth and breadth first solvers on various logic puzzles
