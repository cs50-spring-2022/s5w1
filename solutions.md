# Section 1 Activity Solutions

- Write date to file.

```bash
  date | cut -d" " -f 1,2,3,6 > [username].out
```

- _Append_ name to file.

```bash
  echo "[name]" >> [username].out
```

- How are `cat` and `echo` different?

```bash
  # Essentially:
  #  -  cat reads from a file OR stdin.
  #     (a) read from file.txt, write to stdout
  cat file.txt

  #    (b) receive file contents through stdin, write to stdout
  #         NOTE: This is redundant here, just pass file to `cat`.
  cat < file.txt

  #    (c) read immediate text (i.e. "here document) until specified sequence. Write all the text (minus escape sequence) to stdout.

  # cat <<EOF (without escapes)
  cat \<\<EOF
  > Hello
  > World!
  > ... you can have more text here ...
  > EOF

  #    (d) read contents from variable through stdin, write to stdout
  mystring="Hello, world!"
  cat <<< $mystring

  #  -  The other reads from the commandline.
  #  -  If you haven't seen the uses of $@ and $1, $2, etc... 
  #  -  You'll see it pretty soon!


  #############
  # echo prints the text it gets on the commandline.
  # echo does not read stdin.

  # Both of these work
  echo "Hello, world"
  echo Hello, world

  # echo a variable
  myvar="Hello, world"
  echo $myvar                  # or echo "$myvar"

  # echo does not read its stdin, or files
  echo myfile.txt   # prints "myfile.txt"
  echo < myfile.txt # prints nothing -- contents go to stdin, echo ignores stdin

  # like above, this also directs text to stdin, which echo ignores.

  # echo <<EOF (without escapes)
  echo \<\<EOF
  > Hello
  > world
  > EOF

  # same here
  echo <<< $myvar
```

- sort, numerical, key as field 2, highest to lowest, append to file.

```bash
  sort -k2 -nr data >> [username].out
```
