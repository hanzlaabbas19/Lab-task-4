# Task 1 — Requirement Extraction

| Req. ID | Requirement Description |
| :--- | :--- |
| R1 | Upon system initialization, the robot shall remain in the IDLE state until a delivery request is received. |
| R2 | Upon receiving a valid delivery request, the robot shall transition from IDLE to NAVIGATING toward the designated destination. |
| R3 | While in the NAVIGATING state, if an obstacle is detected, the robot shall temporarily halt normal movement and transition to the AVOIDING_OBSTACLE state. |
| R4 | Upon clearing an obstacle, the robot shall transition from AVOIDING_OBSTACLE back to NAVIGATING toward its destination. |
| R5 | Upon reaching the destination, the robot shall transition from NAVIGATING to DELIVERING and initiate the package drop-off process. |
| R6 | Upon successful package delivery, the robot shall transition from DELIVERING to RETURNING toward the warehouse. |
| R7 | While NAVIGATING or RETURNING, if the battery level drops below a critical threshold, the robot shall immediately abort the delivery and transition to RETURNING. |
| R8 | Upon arriving at the warehouse, the robot shall transition to the IDLE state and wait for subsequent delivery requests. |
| R9 | The robot shall NOT transition directly from IDLE to DELIVERING without first receiving a request and navigating to the destination. |
| R10 | The robot shall NOT transition directly from AVOIDING_OBSTACLE to DELIVERING; obstacle avoidance must resolve back to NAVIGATING first. |
