# shc-for-windows
(shc) Shell script compiler for Windows

works in windows 7 64 bit

ref https://github.com/neurobin/shc/issues/22

### build from [source code](https://github.com/neurobin/shc)

commented out `_SC_ARG_MAX` part in shc.c

then:
```
./configure
make
```

---
anyone know how to use this .exe?

Q: 
```
λ shc -f c.bash -o aaa
shc: invalid first line in script: echo "ssssssdapple"
```
A: You have to put the sha-bang (e.g. #!/bin/bash) at the beginning of the script, since shc need to know which shell is using.
  https://titanwolf.org/Network/Articles/Article?AID=fdf505d4-4924-4c7e-a1bd-2801138aaf67#gsc.tab=0

Q:
```
λ shc -f b.bash -o aaa
shc: invalid file name: /bin/bash No such file or directory
```
A:
use:
```
#!C:/Users/teke/bin/cmder/vendor/git-for-windows/bin/bash.exe
```

Q:
```
λ shc -f b.bash -o aaa
shc Unknown shell (bash.exe): specify [-i][-x][-l]
C:\Users\teke\bin\cmder\bin\shc.exe: No error
```
A:
???
