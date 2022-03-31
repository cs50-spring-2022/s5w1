# Week 1 Section Activity

## Recap

- Basic setup

```bash
  ssh
  git config
  ssh-keygen


  # Speedier login? 
  # Add this into your ~/.ssh/config

  Host cs50
    Hostname plank.thayer.dartmouth.edu
    User f002xxx

  # Mute tfsquota?
  echo  "random text, probably make it relevant?" >  ~/.notfsquota
```

- Existential necessities:

```bash
  ls [-a]
  cd
  echo
  mkdir
  rm, rmdir
  man
  ~
  pwd
  PWD

  cp [-r]
  scp [-r]

  alias
  date

```

- Redirection and pipes.

```bash
  >         # overwrite
  >>        # append

  <         # redirect file into stdin
  <<        # here-document
  <<<       # redirect string variable into stdin

  # File descriptors:
  0 -- stdin
  1 -- stdout
  2 stderr

  <      # redirect file into stdin.
  >      # redirect stdout to file.
  2>     # redirect stderr to file.
  &>     # redirect stdout & stderr to file.
  1>&2   # redirect stdout to stderr
  2>&1   # redirect stderr to stdout

  # You'll often see:
  commmand 2>&1 > filename
```

## Activity

1. Write a command pipeline to get the today's date (`date` util?) in the format `Day Mon Date Year` (think about the commands done in class) and save it into a file `[your_username].out`.

2. _Append_ your name to the file.

3. How are `cat` and `echo` different? Think about why you can:

      - `cat randomfile` to print the contents of file named `randomfile`

      - ...but you can't do the same with echo

4. Anyway,

     - _Append_ a blank line into your file.
     - _Append_ the contents of `data`, ordered by the second field in decreasing order, into the file.
