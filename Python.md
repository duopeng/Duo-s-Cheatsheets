### Pandas
create a single-column dataframe
```
df = pd.DataFrame({'column_title': mylist})
df = pd.DataFrame(data = {'column_title':mylist }, index = mylist2) # with index
```


### add color to stdout
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
