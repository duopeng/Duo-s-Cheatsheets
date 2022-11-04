### Interactive job
```
srun --pty --cpus-per-task=4 --mem=32G bash -l
srun --pty --cpus-per-task=4 --mem=32G --partition=gpu --gpus-per-task 1 bash -l
```

### Reformat squeue output
```
squeue --format=\"%.40i %.9P %.16j %.8u %.8T %.10M %.9l %.6D %R\""
```

### Throttle job arrays
```
scontrol update jobid=X arraytaskthrottle=Y
```

### Batch job
```
#!/bin/bash

#SBATCH --job-name=SRA_download
#SBATCH --time=14-00:00:00
#SBATCH --array=1-44667%200
#SBATCH --nodes=1
#SBATCH --ntasks=1
#SBATCH --mem=8G
#SBATCH --cpus-per-task=1
#SBATCH -e slurm.out/slurm-%A_%a.err
#SBATCH -o slurm.out/slurm-%A_%a.out

# declare arrays
readarray -t accessions < <(cat SRA_accession_list.txt)
declare -x idx=$(( ${SLURM_ARRAY_TASK_ID} -1))
# load conda env
module load anaconda
conda activate sra
#setting directories
working_dir=""
#main 
command ${accessions[$idx]}




```
