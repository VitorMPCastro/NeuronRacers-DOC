
# MLP.gd Documentation

## Overview

**MLP.gd** implements a simple Multi-Layer Perceptron (MLP) neural network as a Godot `Resource`.  
It is designed for use in AI agents, such as controlling cars in neuron-racers.  
The network consists of an input layer, a single hidden layer, and an output layer.

---

## Structure

- **Input Layer:** Receives input features (e.g., sensor data).
- **Hidden Layer:** Processes inputs with learned weights and biases.
- **Output Layer:** Produces control signals (e.g., steering, throttle).

---

## Properties

| Name      | Type                  | Description                                      |
|-----------|-----------------------|--------------------------------------------------|
| input_size| `int`                 | Number of input neurons                          |
| hidden_size| `int`                | Number of hidden neurons                         |
| output_size| `int`                | Number of output neurons                         |
| w1        | `PackedFloat32Array`  | Weights from input to hidden layer               |
| b1        | `PackedFloat32Array`  | Biases for hidden layer                          |
| w2        | `PackedFloat32Array`  | Weights from hidden to output layer              |
| b2        | `PackedFloat32Array`  | Biases for output layer                          |

---

## Methods

### `_init(p_input_size: int, p_hidden_size: int, p_output_size: int)`
Initializes the network with the given layer sizes.  
Weights and biases are randomly initialized in the range [-1, 1].

### `activate(x: float) -> float`
Applies the hyperbolic tangent (`tanh`) activation function.

### `forward(inputs: Array) -> Array`
Performs a forward pass through the network:
- Computes hidden layer activations.
- Computes output layer activations.
- Returns the output as an array.

### `clone() -> MLP`
Creates a deep copy of the network, duplicating all weights and biases.

### `_to_string() -> String`
Returns a string representation of the network's parameters.

---

## Example Usage

```gdscript
var mlp = MLP.new(5, 10, 2)
var result = mlp.forward([0.1, 0.2, 0.3, 0.4, 0.5])
print(result)
```

---

## Notes

- All weights and biases are initialized randomly between -1 and 1.
- The network does not support training; weights are evolved or mutated externally.
- Designed for fast inference in real-time game environments.

---

## License

This file is part of the neuron-racers project.  
See project license for details.