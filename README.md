# Cluster Autoscaler

## Scenario
We need a script to automatically scale our K8s deployment based on CPU load.
The configuration is passed strictly via Environment Variables to follow the 12-factor app methodology.

## Input Environment Variables
- `CPU_USAGE` (int): Current CPU usage percentage (0-100).
- `MAX_REPLICAS` (int): Maximum number of replicas allowed.
- `DRY_RUN` (boolean): If true, just print the action; do not execute.

## Task
Write `autoscaler.py` that:
1. Reads these variables.
2. If `CPU_USAGE` > 80 and current replicas < `MAX_REPLICAS`, scale up.
3. If `DRY_RUN` is enabled, print "[DRY RUN] Scaling..." otherwise print "Executing Scaling...".
