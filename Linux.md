### check peak memory of a process
####
```
/usr/bin/time -v command_to_start_the_process
#then check the "Maximum resident set size (kbytes)" in the output
```

### wget
#### change progress reporting chunck size
```
--progress=dot:giga  #"giga" style: eachdot represents 1M retrieved, there are eight dots in a cluster, and 32 dots (32M) on each line
--progress=dot:mega  #"mega" style: eachdot represents 64k retrieved, there are eight dots in a cluster, and 48 dots (3M) on each line
--progress=dot -e dotbytes=100M  #prints a dot for every 100M of output. You can use other values.
```
#### misc
```
--continue #Continue getting a partially-downloaded file.
--no-check-certificate
```
