# todo

_ _ _

## Useage

**todo** [*FLAG*...] [*OPTION* *VALUE*...]

## Flags

| Short | Long      | Description                            |
| :---- | :---      | :----------                            |
| -a    | --add     | Creates a new list-item                |
| -c    | --check   | Checks off item                        |
| -h    | --help    | Prints this message                    |
| -n    | --new     | Creates a list                         |
| -q    | --quiet   | Silence all messages                   |
| -s    | --show    | Show a list                            |
| -t    | --test    | Runs tests                             |
| -u    | --uncheck | Unchecks item                          |
| -v    | --verbose | Prints verbose messages during runtime |

## Options

| Short | Long      | Value   | Description                                       |
| :---- | :---      | :----   | :----------                                       |
| -i    | --item    | NUMERIC | Selects an item within a list by number NUMERIC   |
| -l    | --list    | STRING  | Selects a list by path STRING (w/o file extension |
| -m    | --message | STRING  | Selects an item within a list by message STRING   |

## Exit Codes

| Number | Description                              |
| :----- | :----------                              |
| 0      | Program ran successfully                 |
| 2      | Option underflow                         |
| 3      | Missing list name                        |
| 4      | Missing list-item message                |
| 5      | Missing list-item number                 |
| 6      | File already exists                      |
| 7      | File does not exist                      |
| 8      | Path failed to derive from --list option |

## Examples

### Create and display list

```bash
# create list then show
todo -nl test;
todo -sl test;
```

```txt
Created On: 2022-01-11T11:40:05EST
Last Edit : 2022-01-11T11:40:05EST

_ _ _

```

### Add an item to list

```bash
# add an item to list
todo -al test -m "First item";
todo -sl test;
```

```txt
Created On: 2022-01-11T11:40:05EST
Last Edit : 2022-01-11T11:42:37EST

_ _ _

1. [ ] First item
```

### Check an item off of list

```bash
# check off an item on list
todo -cl test -i 1;
todo -sl test;
```

```txt
Created On: 2022-01-11T11:40:05EST
Last Edit : 2022-01-11T11:43:51EST

_ _ _

1. [x] First item
```

### Previous examples in a single command

```bash
# start over and do all in one command
rm test.md;
todo -nl test -am "First item" -ci 1 -s;
```

```txt
Created On: 2022-01-11T11:46:53EST
Last Edit : 2022-01-11T11:46:53EST

_ _ _

1. [x] First item
```
