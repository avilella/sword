# sword
tool for finding similar word in a file
# install
install [jvmf1/slib](https://github.com/jvmf1/slib)
```
git clone https://github.com/jvmf1/sword
cd sword
sudo make install
```

If installation method above fails, you can manually do:

```
cc -Wall -Wextra -Werror sword.c -c
cc -lslib sword.o -o sword -l:libslib.so
```

# usage
```
usage: sword [flags] <word>, tries to find similar words in a file
	-d <number>, sets minimum word distance. 3 by default
	-p <path>, sets path to file.
		/usr/local/share/dict/words.txt by default
	-c <delimeter>, char delimeter in file. '\n' by default
	-i, case insensitive
	-r, get text from stdin
```
# examples
```sh
$ sword -p /path/to/wordlist successfull
insuccessful
succesful
successful
successfully
successoral
unsuccessful
unsuccessfully
# you can set a distance with -d flag
$ sword -p /path/to/wordlist -d 1 successfull
succesful
successful
successfully
# you can also pipe into sword
echo 'word' | sword
# or get text from stdin instead
cat /path/to/wordlist | sword -r word
```
