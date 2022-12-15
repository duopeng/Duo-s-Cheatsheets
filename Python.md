### Add color to stdout
```
class bcolors:
    HEADER = '\033[95m'
    OKBLUE = '\033[94m'
    OKCYAN = '\033[96m'
    OKGREEN = '\033[92m'
    WARNING = '\033[93m'
    FAIL = '\033[91m'
    ENDC = '\033[0m'
    BOLD = '\033[1m'
    UNDERLINE = '\033[4m'

print(f"{bcolors.OKGREEN}OK{bcolors.ENDC}")
print(f"{bcolors.FAIL}not found{bcolors.ENDC}")
```
### Jupyter lab
#### Collaborative notebook
```
#Start Jupyter lab on the server:
conda create --name Jlab python=3.9
conda activate Jlab
conda install -c conda-forge jupyterlab
python -m pip install jupyterlab-link-share

#Do port forwarding on the client terminal:
ssh -L 8888:localhost:8888 first.last@server.address
```

### Subprocess
#### write stdout to file, print stderr to screen
```
import subprocess as s
cmd = [command, arg1, arg2, arg3]
out = open(filename, "wb")
p = s.Popen(cmd, universal_newlines=True, stdout=out, stderr = s.PIPE)
mystderr = p.stderr.read()
print(mystderr)
```


### Pandas
create a single-column dataframe
```
df = pd.DataFrame({'column_title': mylist})
df = pd.DataFrame(data = {'column_title':mylist }, index = mylist2) # with index
```
iterater over df by rows
```
for index, row in df.iterrows():
    #do something
```


### Files
#### Copy files
```
import shutil
shutil.copyfile(src, dst)
# 2nd option
shutil.copy(src, dst)  # dst can be a folder; use shutil.copy2() to preserve timestamp
```
#### read files
```
oneline = fileHandle.readline() #read oneline
entirefile = fileHandle.read() #read entire file
```
#### Check gzip file integrity
```
def check_gzip_integrity(filepath):
    import gzip
    chunksize = 1024 * 1024
    with gzip.open(filepath) as g:
        try:
            while g.read(chunksize):
                pass
            return True
        except:
            #print("Corrupted!", e)
            return False
```

### Conda
creat environment
```
conda create --name py39 python=3.9
```
creat environment from file
```
conda env create -f environment.yml
```
rename environment
```
conda rename -n old_name -d new_name
```

