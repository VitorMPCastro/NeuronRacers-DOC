# CarData

**File:** `scripts/car/carData.gd`  
**Class:** `CarData` (extends `CharacterBody2D`)

## Overview

`CarData` is a telemetry and statistics container for each car agent in the neuron-racers simulation. It tracks speed, distance, timing, fitness, and checkpoint progress, providing essential data for evaluation and training.

---

## Properties

- **top_speed**: `float`  
  Highest speed reached by the car. Only updated if the new value is greater than the current.

- **total_distance**: `float`  
  Total distance traveled by the car.

- **timestamp_spawn**: `float`  
  Global time when the car was spawned.

- **timestamp_death**: `float`  
  Global time when the car died. Defaults to `-1.0` (alive).

- **time_alive**: `float` (getter)  
  Time the car has been alive, calculated as  
  `GameManager.global_time - timestamp_spawn` if alive,  
  or `timestamp_death - timestamp_spawn` if dead.

- **fitness**: `float`  
  Fitness score for evolutionary algorithms.

- **collected_checkpoints**: `Array`  
  List of checkpoints collected by the car.

- **sector_times**:  
  Stores timing data for each sector (type not specified). #WIP

---

## Usage

Each car instance contains a `CarData` object to record its progress and statistics throughout a race or simulation. Managers and evaluation systems use this data for fitness calculation, telemetry, and progress tracking.

---

## Related Files

- [`Car`](car.gd): Main car agent that owns a `CarData` instance.
- [`GameManager`](../manager/gameManager.gd): Provides global timing.
- [`AgentManager`](../manager/agentManager.gd): Uses fitness and progress data.

---

## Example

```gdscript
var car_data = CarData.new()
car_data.top_speed = 120.0
car_data.timestamp_spawn = GameManager.global_time
# ... update during simulation ...
print(car_data.time_alive)
```

---

## Notes

- The class is designed for use as a data container, not as a physical entity, despite extending `CharacterBody2D`.
- `sector_times` and `collected_checkpoints` should be initialized as needed in your code.
