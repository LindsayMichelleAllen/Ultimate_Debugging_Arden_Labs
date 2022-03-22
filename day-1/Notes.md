* Go stdlib has a package called "runtime" <- runtime.Breakpoint() (triggers SIGTRAP unless a debugger is attached)  
- `dlv exec <path-to-executable-you-want-to-debug>`

* need to use non-optimized compiled binaries for debugging (use gcflags parameter to specify)

* `strace` (outputs all system calls while the program is running) system call stuff that's probably useful
- delve has a similar function for YOU defined functions `dlv trace <function-name> --stack<#-of-frames-you-want-to-see>` (still in development) (can use regex for function name)

### Basics of using debuggers

* Start with call stack

### In delve:
- `transcript <filename>`  <- compiles and creates binary optimized for debugging, starts program and attaches to it
- If changes are made, run `rebuild` within debug session to recompile and restart
- `clearall` clears all breakpoints
- `restart` restarts the program
- `restart <input>` restarts the program with given input
- `print <thing>` can be used with variables and errors
- `break <filename>:<line#>` - sets a breakpoint
- `funcs <struct-type>` prints list of functions for given struct type



### Intro into CLI usage (debugging that requires user input)
- `--headless` use delve server without cli
- `list <int>` list the last <int> lines of code
- `watch -w <variable>` stops at watchpoint when value of <variable> changes
- `cond <breakpoint#> node == nil` set a condition for a breakpoint (only fire if this condition is met)


### Getting familiar with debugging mindset

### How debuggers work

## Attach debugger to running server (under cmds/attach)
- `dlv attach <process-id-of-program>` when ataching to a process that's running - debugger will stop the program until you issue `continue`
- `Ctrl + C` to pause execution and get back to (dlv) cli
How to ref anonymous function?
- use funcs command - should display as func1, func2.. or something similar
- when debug session is done, Ctrl + C will stop debug but delve will not kill a running process it didn't start unless specified 