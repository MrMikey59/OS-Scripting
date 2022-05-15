# BASH - a Linux Command Terminal  

What is .bashrc? Does GitBash support it?  

Commands will often return output using `STDOUT`, errors through `STDERR`, and a Return Code to report errors in a more script-friendly manner.  
The return code or exit status is the way scripts/commands have to communicate how execution went.  
A value of 0 usually means everything went OK; anything different from 0 means an error occurred.  
In general, bash scripts are useful for short and simple one-off scripts when you just want to run a specific series of commands. bash has a set of oddities that make it hard to work with for larger programs or scripts:

- bash is easy to get right for a simple use case but it can be really hard to get right for all possible inputs. For example, spaces in script arguments have led to countless bugs in bash scripts.
- bash is not amenable to code reuse so it can be hard to reuse components of previous programs you have written. More generally, there is no concept of software libraries in bash.
- bash relies on many magic strings like `$?` or `$@` to refer to specific values, whereas other languages refer to them explicitly, like `exitCode` or `sys.args` respectively. 

#### What is the difference between `source script.sh` and `./script.sh`

In both cases the `script.sh` will be read and executed in a bash session, the difference lies in which session is running the commands.
For `source` the commands are executed in your current bash session and thus any changes made to the current environment, like changing directories or defining functions will persist in the current session once the `source` command finishes executing.
When running the script standalone like `./script.sh`, your current bash session starts a new instance of bash that will run the commands in `script.sh`.
Thus, if `script.sh` changes directories, the new bash instance will change directories but once it exits and returns control to the parent bash session, the parent session will remain in the same place.
Similarly, if `script.sh` defines a function that you want to access in your terminal, you need to `source` it for it to be defined in your current bash session. Otherwise, if you run it, the new bash process will be the one to process the function definition instead of your current shell.

## Aliases
As you can imagine it can become tiresome typing long commands that involve many flags or verbose options. Nevertheless, most shells support **aliasing**. For instance, an alias in bash has the following structure (note there is no space around the `=` sign):
```bash
alias alias_name="command_to_alias"
```

1. Create an alias `dc` that resolves to `cd` for when you type it wrongly.
2.  Run `history | awk '{$1="";print substr($0,2)}' | sort | uniq -c | sort -n | tail -n 10`  to get your top 10 most used commands and consider writing shorter aliases for them. Note: this works for Bash; if you're using ZSH, use `history 1` instead of just `history`.

## Arguments
BASH uses a variety of special variables to refer to arguments, error codes, and other relevant variables. Below is a list of some of them. A more comprehensive list can be found [here](https://tldp.org/LDP/abs/html/special-chars.html).  
- `$0` - Name of the script  
- `$1` to `$9` - Arguments to the script. `$1` is the first argument and so on.  
- `$@` - All the arguments  
- `$#` - Number of arguments  
- `$?` - Return code of the previous command  
- `$$` - Process identification number (PID) for the current script  
- `!!` - Entire last command, including arguments. A common pattern is to execute a command only for it to fail due to missing permissions; you can quickly re-execute the command with sudo by doing `sudo !!`  
- `$_` - Last argument from the last command. If you are in an interactive shell, you can also quickly get this value by typing `Esc` followed by `.` or `Alt+.`  

## Exit Codes
Exit codes can be used to conditionally execute commands using `&&` (and operator) and `||` (or operator), both of which are [short-circuiting](https://en.wikipedia.org/wiki/Short-circuit_evaluation) operators. Commands can also be separated within the same line using a semicolon `;`.  

The `true` program will always have a 0 return code and the `false` command will always have a 1 return code.  

```bash
false || echo "Oops, fail"
# Oops, fail

true || echo "Will not be printed"
#

true && echo "Things went well"
# Things went well

false && echo "Will not be printed"
#

true ; echo "This will always run"
# This will always run

false ; echo "This will always run"
# This will always run
```

