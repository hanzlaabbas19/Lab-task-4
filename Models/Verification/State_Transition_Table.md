# Task 5 — Verification Activity Answers

### Check 1 — Invalid Transition (IDLE → DELIVERING)
* **Can this happen?** No, the system design prohibits this direct jump.
* **Requirement Violated:** R9 ("The robot shall NOT transition directly from IDLE to DELIVERING..."). The robot must transition to NAVIGATING first.

### Check 2 — Missing Transition (NAVIGATING → AVOIDING_OBSTACLE without return path)
* **What happens?** The system experiences a dead-lock or soft-lock state.
* **Can the robot continue its delivery?** No. Without the AVOIDING_OBSTACLE → NAVIGATING transition, the robot remains stuck in the obstacle-avoidance loop indefinitely and can never reach the destination or resume navigation.

### Check 3 — Obstacle During Delivery (AVOIDING_OBSTACLE → DELIVERING)
* **Can the robot move directly from AVOIDING_OBSTACLE to DELIVERING?** No. 
* **Reason:** This violates R10. Even if the obstacle is detected right next to the target location, the robot must complete its avoidance routine and transition back to NAVIGATING to formally register arrival at the destination before entering DELIVERING.
