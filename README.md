# igrep (Interactive grep)
A small tool to find a string in a directory interactively

## Prerequisites
* Python 3
* Linux
* vim

## Why?
Finding some string in a set of files/directories is a common task. It's trivial to achieve everything using recursive `grep`.
In fact, this tool uses the same old dependable `grep` tool. However, most of the times we search these words in order
to see the context in which they are being used (not a single line of context).

Most of the times, I ended up copy-pasting the filename and opening the file and searching for the word. If I am interested in the word appearing in 4 files,
I ended up opening 4 files by copy-pasting the path and searching for the word within the file (using vim search). So, why not automate the task when we know what repeats! That's all this tool does but interactively.
Nothing more nothing less. It's the same old `grep` with a wrapper.

## How to use?

**Basic usage**<br/>
![Using igrep](/screenshots/igrep_usage.png?raw=true "Using igrep")

**Results**<br/>
![igrep result](/screenshots/igrep_usage_result.png?raw=true "Result of igrep")

**Usage checks**<br/>
![Wrong igrep parameters](/screenshots/igrep_wrong_usage.png?raw=true "Providing wrong igrep parameters")

#### Options

```bash
$ ./igrep --help
usage: igrep [-h] -s SEARCH_TERM -d DIRECTORY [-w] [-i] [-v]

optional arguments:
  -I INCLUDE, --include INCLUDE
                        Comma separated file extensions to include
  -h, --help            show this help message and exit
  -w, --whole-word      Search whole words only
  -i, --ignore-case     Ignore case in search
  -v, --version         show program\'s version number and exit

required named arguments:
  -s SEARCH_TERM, --search-term SEARCH_TERM
                        Term to search
  -d DIRECTORY, --directory DIRECTORY
                        Directory to search
```

#### Examples

```bash
# Search in files with extensions '.c' or '.h' or '.cpp'
$ ./igrep -I "c,h,cpp" -s search_term -d search_directory

# Search a term ignoring the case
$ ./igrep -i -s search_term -d search_directory

# Search a term where the whole term appears
$ ./igrep -w -s search_term -d search_directory

```

## Installation
No installation, just download the script or clone the repository. Provide
execute permissions to the script. The simplest way to use is by adding your `igrep` tool path to your `$PATH`.
For example, if you've cloned the repository to `/home/<username>/Downloads/igrep`

```bash
# Provide execute permissions
$ chmod +x /home<username>/Downloads/igrep/igrep

# Add the script path to the environment paths
# Add the below line to your ~/.bashrc if you wish to presist the changes on restart
$ export PATH:$PATH:/home/<username>/Downloads/igrep
```

## FYI
The tool excludes `.svn`, `.git`, `BUILD` directories and `*.swp` and `*.o` files from search results by default. Additional option to exclude directories will be added in future

## FAQ

**[Q]** But we already have these tools, why reinvent the wheel?<br/>
**[A]** Cool, create an issue and let me know the tool

**[Q]** I can accomplish the same using the readily available `find`, `grep`, `xyz` etc.
There was no need to create this. It's redundant, bulky and not useful<br/>
**[A]** Technically, that's not a question. So, I'll pass. Oh, BTW it's useful to me

**[Q]** There's already another `igrep` repository which does much more<br/>
**[A]** Again, that's not a question. Feel free to use it though

**[Q]** Why don't you upload it to PyPi?<br/>
**[A]** Let's not make this whole thing unnecessarily bulky. Just download the script and use it

