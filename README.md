Bluesubmit
=================
A tool to parse Codeforces problems and submit solutions using Linux terminal.

## Installation
 The tool has dependencies on the following python packages - Click, robobrowser, requests. To install them you may either create a virtual environment or install them globally. Remember that you would need the virtual environment activated each time you use the tool.
 ```bash
 pip install Click
 pip install robobrowser
 pip install requests
 pip install python-memcached
 ```
 Additionally, it also depends on the package [memcached](https://memcached.org/). Memcached is used to store the logged in session in cache, so that logging in again is not required while submitting a solution. The download in available in the link and also in the Arch User Repository and the Debian apt repositories. You may additionally require to start the memcached service by
 ```
 sudo systemctl enable memcached.service
 sudo systemctl start memcached.service
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
### Parsing the contest
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

### Logging in and submitting solutions
To submit your solutions, first to you need to enter the Codeforces system. To do this type
```bash
enter
```
Now enter your login credentials and you are good to go to submit the solutions.
Note that you need to enter Codeforces just once, and logging in again will be required only when you restart your system.

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
- [Codeforces Parser](https://github.com/johnathan79717/codeforces-parser)
- [idne](https://github.com/endiliey/idne)
