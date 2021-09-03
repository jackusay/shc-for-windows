# shc-for-windows
(shc) Shell script compiler for Windows

**error**

works? in windows 7 64 bit

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
my script:
```
#!C:/Users/teke/bin/cmder/vendor/git-for-windows/bin/bash.exe
echo "ssssssdapple"
```
result:
```
λ shc -f b.bash -o aaa
shc Unknown shell (bash.exe): specify [-i][-x][-l]
C:\Users\teke\bin\cmder\bin\shc.exe: No error
```
A:
???

---
in mingw64

my code:
```
#!/bin/bash
echo "ssssssdapple"
```

make install:
```
taye@taye-PC MINGW64 /c/Users/taye/Downloads/xxx5
$ make install
Making install in src
make[1]: Entering directory '/c/Users/taye/Downloads/xxx5/src'
make[2]: Entering directory '/c/Users/taye/Downloads/xxx5/src'
 /usr/bin/mkdir -p '/usr/local/bin'
  /usr/bin/install -c shc.exe '/usr/local/bin'
make[2]: Nothing to be done for 'install-data-am'.
make[2]: Leaving directory '/c/Users/taye/Downloads/xxx5/src'
make[1]: Leaving directory '/c/Users/taye/Downloads/xxx5/src'
make[1]: Entering directory '/c/Users/taye/Downloads/xxx5'
make[2]: Entering directory '/c/Users/taye/Downloads/xxx5'
make[2]: Nothing to be done for 'install-exec-am'.
 /usr/bin/mkdir -p '/usr/local/share/man/man1'
 /usr/bin/install -c -m 644 shc.1 '/usr/local/share/man/man1'
make[2]: Leaving directory '/c/Users/taye/Downloads/xxx5'
make[1]: Leaving directory '/c/Users/taye/Downloads/xxx5'
```
```
taye@taye-PC MINGW64 /c/Users/taye/Downloads/xxx5
$ shc -f d.bash
No such file or directory
shc: invalid file name: /bin/bash
```
???

```sh
#!/bin/bash.exe
echo "ssssssdapple"
```

result:
```
$ shc -f d.bash
C:\msys64\usr\local\bin\shc.exe: No error
shc Unknown shell (bash.exe): specify [-i][-x][-l]
```
???

---

others pc:

```
λ shc
/c/Users/user/bin/cmder/bin/shc: line 7: syntax error near unexpected token `newline'
/c/Users/user/bin/cmder/bin/shc: line 7: `<!DOCTYPE html>'
```
???
