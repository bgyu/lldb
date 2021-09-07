# lldb
Most used lldb commands
--------------------------------------------------

# Starting lldb
```bash
lldb a.out

# with args
lldb -- a.out arg1 arg2

(lldb) file a.out
```

# Help
```bash
(lldb) help

# help on specific sub commands
(lldb) help breakpoint
(lldb) help watchpoint
(lldb) help source
```

# Running
``` bash
(lldb) run
# or short style
(lldb) r
```

# Setting breakpoint
``` bash
# set breakpoint on file main.cpp at line 30
(lldb) breakpoint set -f main.cpp -l 30

# or short style
(lldb) br s -f main.cpp -l 30
# or enen shorter style
(lldb) b main.cpp : 30

# Breakpoints with Symbols
# On a function
(lldb) b square(int)
# On a class method
(lldb) b Demo::demo()
# Inside a namespace
(lldb) b LLDBDemo::add(int)

# List breakpoints
(lldb) br list

# delete breakpoint with number 1, can use `br list` to show all breakpoints first then delete based on number
(lldb) br delete 1

# delete all breakpoints
(lldb) br del
```

# Steping around
```bash
# stepping over
(lldb) next
(lldb) n

# stepping into
(lldb) step
(lldb) s

# continue
(lldb) continue
(lldb) c
```

# Print variable contents
```bash
# print the content of a
(lldb) print a

# frame variables (local variables)
(lldb) frame variable
(lldb) fr v
```

# Call stack (backtrace)
```bash
(lldb) bt

# select frame 2
(lldb) fr select 2

# select top frame 0 (the top of current stack)
(lldb) fr select 0

# switch frame 3, shortcut version
(lldb) f 3

# go back to the current frame
(lldb) fr select
```

# Watch points
Note: program must be running to set watch points
```bash
# when variable `a` gets changed, the pragram will stop at where it changed
(lldb) watchpoint set variable a

# you can also monitor read, write or read_write on variable `a`
(lldb) watchpoint set variable -w read | write | read_write

# watch member variable (short version) `obj.m_count`
# w -> watchpoint, s -> set, v -> variable
(lldb) w s v -w read obj.m_count

# delete watchpoint 1
(lldb) watchpoint delete 1
```

# Kill process and exit
```bash
# kill current debugging process
(lldb) kill
# quit lldb
(lldb) quit
```

