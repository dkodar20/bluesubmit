Bluesubmit
=================
A fork of [Codeforces Parser](https://github.com/johnathan79717/codeforces-parser) with added functionality of submitting code through _CLI_.

## Installation
 The tool has dependencies on the following python packages - Click, robobrowser, requests. To install them you may either create a virtual environment or install them globally. Remember that you would need the virtual environment activated each time you use the tool.
 ```bash
 pip install Click
 pip install robobrowser
 pip install requests
 ```
 To use this tool, clone this repository to your system and add the directory to path variables.
 You may also consider adding all the files and folders of the repository to an already existing path.

 Note - Remember changing the path of the Template in `cf-sample-gen` to it's complete path starting from root (like `/etc/bluesubmit/utils/main.cc`).

 Go to utils/config.py and enter your username and password.
 ```python
 username = "whomesoever" # your codeforces username
 password = "abcdef" # your password
 ```

## Usage
Parse the contest
```bash
cf-sample-gen 1469
```
This will create directories with names as A, B, C, D and so on, each of which has the problem file, sample inputs and outputs parsed from the problem. Additionally each of the problem directories will have a `test.sh` file whivh is used in checking solution against the sample cases.
To run your code against the sample test cases, navigate to your problem directory and execute the `test.sh` file as follows -
```bash
./test.sh
```
You may also add your own additional debugging flags in `cf-sample-gen`. Add a `-d` flag after `test.sh` to run your code with the debugging flags.
```bash
./test.sh -d
```
To submit the code which is parsed from the bluesubmit tool just type
```bash
submit
```
in the problem directory after you are done with soltuion. This will submit your code on codeforces and tell the verdict of solution. Remember that you should not remove and/or change the problem ID at the beginning of each file.

To submit some random code you have to specify the Problem ID and filename in the terminal as well.
```bash
submit --id=1469A --file=A.cc
```

## Todos
- Individual problem parsing

# Credits
- Forked from [Codeforces Parser](https://github.com/johnathan79717/codeforces-parser)
- [idne](https://github.com/endiliey/idne)
