# Explicit-Malloc

Explicit-Malloc is a library that allows explicit display of allocation of memory when using the original malloc. 

## Getting Started

go to the directory where you can see `Explicit-Malloc.zip`
```
run the following command
unzip Explicit-Malloc.zip
gcc -fPIC -shared -o explicit_malloc.so explicit_malloc.c -ldl
LD_PRELOAD=(full path of explicit_malloc.so) (program where malloc will be replaced)  
```
### Prerequisites 
```
System: Linux
Compiler : gcc
```
## Running the tests

```
LD_PRELOAD=(full path of explicit_malloc.so) (full path of ./test)
```

## Warning
```
The library does not take account of the deallocation of memory.
Only memory allocated by `malloc` will be displayed.
```
## Authors
  Rory(Qianyi Shu)
