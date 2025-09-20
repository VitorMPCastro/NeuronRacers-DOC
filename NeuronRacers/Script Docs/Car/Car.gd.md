# Car

**File:** `scripts/car/car.gd`  
**Class:** `Car` (extends `CharacterBody2D`)

## Overview

The `Car` class represents a vehicle agent in the neuron-racers simulation. It supports both AI and player control, simulates realistic car physics, and tracks its own progress, fitness, and state for evolutionary training.

---

## Exported Properties

- **steering_angle**: Maximum steering angle (degrees).
- **engine_power**: Engine force applied for acceleration.
- **friction**: Friction coefficient.
- **drag**: Air drag coefficient.
- **braking**: Braking force.
- **max_speed_reverse**: Maximum speed in reverse.
- **slip_speed**: Speed threshold for reduced traction (drifting).
- **traction_fast**: Traction at high speed.
- **traction_slow**: Traction at low speed.
- **wheel_base**: Distance between front and rear wheels.
- **is_player**: If true, car is controlled by player input.
- **use_ai**: If true, car is controlled by AI.

---

## Runtime Variables

- **crashed**: Indicates if the car has crashed.
- **acceleration**: Current acceleration vector.
- **steer_direction**: Current steering direction (radians).
- **camera_follow**: If true, camera follows this car.
- **car_data**: Stores car telemetry and progress.
- **control_module**: Reference to control logic (AI or player).
- **brain**: AI neural network (`MLP`).
- **total_speed**: Accumulated speed for average calculation.
- **time_alive**: Time since spawn (from `car_data`).
- **fitness**: Fitness score (from `car_data`).
- **origin_position**: Starting position.
- **max_distance**: Furthest distance from origin.
- **last_position**: Previous position for progress tracking.

---

## Signals

- **car_death**: Emitted when the car dies/crashes.
- **car_spawn**: Emitted when the car is spawned.

---

## Main Methods

### Lifecycle

- **_ready()**: Connects signals and emits spawn event.
- **_on_spawn()**: Initializes car state and registers with race manager.
- **_on_death()**: Handles car death (visuals, disables physics).
- **die()**: Emits `car_death` signal.

### Physics & Movement

- **_physics_process(delta)**: Handles input, steering, physics, progress, and collision.
- **handle_input()**: Processes AI or player input for movement.
- **apply_friction(delta)**: Applies friction and drag to velocity.
- **calculate_steering(delta)**: Updates steering and velocity based on wheel positions and traction.

### AI & Sensors

- **get_sensor_data()**: Returns normalized distances from RayCast2D sensors for neural network input.

### Progress & Telemetry

- **get_average_speed()**: Returns average speed over lifetime.
- **collect_telemetry()**: Updates top speed (for logging/debug).

### Checkpoints & Progress

- **_on_cross_checkpoint(checkpoint)**: Updates checkpoint collection.

### Utility

- **_to_string()**: Returns a string summary of car state.

---

## Usage

Cars are spawned and managed by `AgentManager`. They interact with `RaceProgressionManager` for progress tracking and fitness calculation. AI cars use an `MLP` brain for control; player cars respond to input actions.

---

## Related Files

- [`CarData`](carData.gd.md): Stores telemetry and progress for each car.
- [`MLP`](../ai/MLP.gd): Neural network for AI control.
- [`AgentManager`](../manager/agentManager.gd): Handles population and evolution.
- [`RaceProgressionManager`](../manager/raceProgressionManager.gd): Tracks race progress.

---

## Example

```gdscript
var car = Car.new()
car.use_ai = true
car.brain = MLP.new(5, 8, 2)
add_child(car)
```

---

## Notes

- Car physics are handled manually for realism.
- Sensor data is collected from child RayCast2D nodes for AI input.
- Fitness and progress are updated externally by managers.
