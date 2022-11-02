### interactive job
```
srun --pty --cpus-per-task=4 --mem=32G bash -l
srun --pty --cpus-per-task=4 --mem=32G --partition=gpu --gpus-per-task 1 bash -l
```

### reformat squeue output
```
squeue --format=\"%.40i %.9P %.16j %.8u %.8T %.10M %.9l %.6D %R\""
```

### throttle job arrays
```
scontrol update jobid=X arraytaskthrottle=Y
```
