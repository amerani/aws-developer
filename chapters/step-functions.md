# Step Functions
- arrange and visualize components as series of steps
- trigger, track and retry each step
- logs state of each step

## Sequential Steps
```
start -> upload -> save -> end
```

## Branching Steps
```
              -> convert to jpeg 
             /                  \
start -> select                   -> load in db -> end
             \                  /
              -> convert to png
```

## Parallel Steps
```
                 |-> extract metadata   |
start -> process |-> resize image       | -> load in db -> end
                 |-> facial recognition |
```
