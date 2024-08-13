# Logic Simulator
## Overview

This project is a simple logic simulator designed to simulate logic circuits and compute the outputs of different designs. It provides the capability to define nodes and gates, and then simulate the behavior of a logic circuit based on the specified inputs and operations.
Features

    Node Class: Represents a node in the circuit with name and value attributes. Provides logical operations (AND, OR, XOR) between nodes.
    Gate Class: Represents logic gates (AND, OR, NAND, NOR, XOR, XNOR, NOT) that operate on two input nodes and produce an output node.
    Simulator Class: Manages the circuit simulation, including handling gates and nodes, running simulations, and retrieving outputs.
    GateGenerator Class: Handles the creation of nodes and gates based on input, and manages their integration into the simulation.

## Classes and Methods
### Node Class

    Attributes:
        name: The name of the node (e.g., A, B).
        value: The value of the node (0 or 1).
    Methods:
        Constructors: Default and parameterized constructors.
        Setters and Getters for name and value.
        AND(), OR(), XOR(): Logical operations between two nodes.
        Overloaded ostream << operator to print node information.

### Gate Class

    Attributes:
        input1, input2: Input nodes.
        output: Output node.
    Methods:
        Constructors: Default and parameterized constructors.
        Setters and Getters for input and output nodes.
        Logical gate operations: AND, OR, NAND, NOR, XOR, XNOR, NOT.
        simulateGate(): Returns the logical value of the gate based on its type.

### Simulator Class

    Attributes:
        gates: Vector of pointers to Gate objects.
        nodes: Vector of pointers to Node objects.
    Methods:
        postGate(): Adds a gate to the simulator.
        postNode(): Adds a node to the simulator.
        FindNode(): Finds and returns a node by its name.
        startSimulate(): Starts the simulation by processing all gates.

### GateGenerator Class

    Methods:
        parseInput(): Parses the input and directs it to the appropriate logic.
        createNode(): Creates and returns a new Node object.
        createGate(): Creates and returns a new Gate object based on the specified type.

## Usage
### Input Format

The input consists of:

    Gate Definitions: Specifies the gate type (e.g., AND, OR) and the nodes it operates on.
    Set Values: Assigns values (0 or 1) to input nodes.
    Simulation Command: Initiates the simulation process.
    Output Command: Displays the output of a specific node or all nodes.

## Example

text

AND A B D
OR C D E
SET A 1
SET B 0 
SET C 1
SIM 
OUT E
OUT ALL

Sample Output

text

E: 1
A: 1
B: 0
D: 0
C: 1
E: 1

## Constraints

    Avoid using C-style casting.
    Do not use void pointers.
    Friend functions or classes are restricted, except for overloading ostream.
    Ensure functions and variables are appropriately encapsulated (public, private, protected).
    The code should compile with 0 warnings.

Dependencies

This project is implemented in C++. Ensure you have a C++ compiler set up on your system.
