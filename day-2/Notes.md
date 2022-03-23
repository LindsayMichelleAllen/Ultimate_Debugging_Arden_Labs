** SHOW HOW TO DEBUG GOROUTINES
`goroutine <#> stack`  <-- show stack trace of goroutine
`goroutine <#>`        <-- switch to goroutine

Jesus you can do this with threads too

stack -full will show variable values with each stack frame


### Debug commands within debug session


** talk about stdin redirection with delve
--tty (redirect from terminal)
-r (redirect from stdin)

`continue <function-name>` <-- set a break point at function and continue execution (can also do this with line numbers)

`step` / `stepout`         <-- step in and out of functions

`disassemble`              <-- shows cpu instructions
`step-instruction`         <-- moves forward 1 cpu instruction

`disassemble -l <function-name>`  <-- disassemble at that function

can name breakpoints: `break <breakpoint-name> <location>`

`on <breakpoint> <command>` - execute a command when a breakpoint is hit

can turn breakpoints into tracepoints

`whatis <variable>`        <-- returns variable type


### How to debug core dumps
can make a snapshot of a core dumb without actually killing the program

`bt` - backtrace (looks like stack)