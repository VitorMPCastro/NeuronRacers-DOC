# AgentManager

**File Path in project:** [`scripts/manager/agentManager.gd`](scripts/manager/agentManager.gd)  
**Class:** `AgentManager` (extends `Node2D`)

## Overview

`AgentManager` controls the lifecycle and evolution of AI agents (cars) in the simulation. It manages population spawning, fitness evaluation, mutation, elitism, and generational progression for a neuroevolution system using multilayer perceptrons ([`MLP`](MLP.gd.md)).

## Exported Properties

- **car_scene**: `PackedScene` — Scene to instantiate for each car.
- **population_size**: `int` — Number of cars per generation.
- **generation_time**: `float` — Duration of each generation.
- **is_training**: `bool` — If true, enables training mode.
- **elitism_percent**: `float` — Fraction of top cars to carry over genes.
- **weight**: `float` — Mutation weight range.
- **mutate_chance**: `float` — Probability of mutating each weight/bias.
- **input_layer_neurons**: `int` — Input layer size for MLP.
- **hidden_layer_neurons**: `int` — Hidden layer size for MLP.
- **output_layer_neurons**: `int` — Output layer size for MLP.
- **print_debug_generation**: `bool` — Print generation debug info.
- **print_new_brains_to_console**: `bool` — Print new brains info.

## Main Variables

- **cars**: Array of car instances.
- **best_cars**: Array of elite cars.
- **best_speed**: Static int, tracks best average speed.
- **generation**: Current generation number.
- **timer**: Generation timer.
- **trackOrigin**: Reference to track origin node.

## Key Methods

### Lifecycle

- **_ready()**: Initializes population if training.
- **_physics_process(delta)**: Updates car fitness.
- **_process(delta)**: Handles generation timing and triggers next generation.

### Population Management

- **spawn_population(brains = [])**: Instantiates cars, assigns brains.
- **clear_scene()**: Frees all cars and resets timer.

### Evolution

- **next_generation()**: Advances generation, applies elitism, mutation, and spawns new population.
- **mutate(brain: MLP)**: Returns a mutated clone of the given brain.

### Fitness & Selection

- **update_car_fitness()**: Updates fitness for each car.
- **weighted_pick(cars, total_fitness)**: Selects a car based on fitness proportion.
- **sort_by_fitness()**: Sorts cars by fitness.
- **get_best_car()**: Returns the best non-crashed car.
- **get_best_speed()**: Updates and returns best average speed.
- **kill_stagnant_car(car)**: Kills cars that are too slow.

### Utility

- **is_all_cars_dead()**: Checks if all cars have crashed.
- **generation_to_string(options)**: Returns a string summary of the current generation.

## Fitness Calculation

Fitness for each car is calculated as:
$$
\text{fitness} = \frac{100}{\text{distance to next checkpoint}} + 1000 \times \text{checkpoints collected}
$$
using [`RaceProgressionManager.get_distance_to_next_checkpoint`](scripts/manager/raceProgressionManager.gd).

## Related Files

- [`MLP`](MLP.gd.md): Neural network used for car brains.
- [`RaceProgressionManager`](scripts/manager/raceProgressionManager.gd): Tracks race progress and checkpoints.
- [`Car`](scripts/car/car.gd): Car node controlled by AI.

## Signals

None defined in this file.

## Usage

Attach `AgentManager` to a node in your scene. Configure exported properties in the editor. When `is_training` is true, the manager will automatically handle population evolution and simulation.
