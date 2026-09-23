# Task 2 — System States

* **IDLE**: The robot is powered on at the warehouse, awaiting a delivery request.
* **NAVIGATING**: The robot is actively moving from the warehouse toward the delivery destination.
* **AVOIDING_OBSTACLE**: The robot has paused standard navigation to maneuver around a detected obstacle.
* **DELIVERING**: The robot has arrived at the destination and is executing package handoff.
* **RETURNING**: The robot is actively traveling back to the warehouse (either after delivery or due to low battery).

  # Task 3 — Events and Conditions

1. **Delivery Request Received**: Triggered when a new destination request is assigned.
2. **Obstacle Detected**: Triggered when proximity sensors detect an object blocking the navigation path.
3. **Obstacle Avoided**: Triggered when sensors confirm the path around the object is clear.
4. **Destination Reached**: Triggered when GPS/location sensors match the target destination coordinates.
5. **Delivery Successful**: Triggered when the package is handed off or dropped off securely.
6. **Critical Battery**: Triggered when battery charge drops below the predefined minimum safety threshold.
7. **Warehouse Reached**: Triggered when GPS/location sensors confirm arrival back at the home warehouse.

   # Task 4 — State Transition Table

| Current State | Event / Trigger | Guard / Condition | Target State |
| :--- | :--- | :--- | :--- |
| IDLE | Delivery Request Received | Battery OK | NAVIGATING |
| NAVIGATING | Obstacle Detected | — | AVOIDING_OBSTACLE |
| NAVIGATING | Destination Reached | Path Clear | DELIVERING |
| NAVIGATING | Critical Battery | Battery < Threshold | RETURNING |
| AVOIDING_OBSTACLE | Obstacle Avoided | — | NAVIGATING |
| DELIVERING | Delivery Successful | — | RETURNING |
| RETURNING | Warehouse Reached | — | IDLE |



