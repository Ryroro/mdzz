# CounterBasicBlock

CounterBasicBlock is an llvm pass that can be used to count the number of basic blocks in a program.

## Getting Started

```
unzip Counterbb.zip

```
Move the unzipped folder to the llvm source folder (where-your-llvm-live/lib/Transforms/)
```
mv Counterbb where-your-llvm-live/lib/Transforms
```
Modify the CMakeLists.txt in `Transforms` folder
```
cd where-your-llvm-live/lib/Transforms
vim CMakeLists.txt (you can modify it with any editor)
```
Add the following to the end of `CMakeLists.txt`.
```
add_subdirectory(Counterbb)
```
Go to the folder where your llvm is built and then run `make` to build llvm again.
```
cd where-llvm-is-built
make
```
Go to the sub-folder to find the compiled pass file.
```
cd where-llvm-is-built/lib
```
On Linux, the generated file is a shared object file and the compiled file is
```
LLVMCounterbb.so
```
On Mac, the generated file is a dynamic linked library and the compiled file is
```
LLVMCounterbb.dylib
```
Either one can work with command `opt`

To count the how many basic blocks there are in program, the program has to be compiled in to .bc code
Compile the target program with the following command.

```
clang -o2 -emit-llvm target-program-name.c -c -o target-program-name.bc
```
To run the LLVMCounterbb.so or LLVMCounterbb.dylib, run the following command.
So on Linux, run:
```
opt -load LLVMCounterbb.so -counterbb < target-program-name.bc > /dev/null
```
On Mac, run:
```
opt -load LLVMCounter.dylib -counterbb < target-program-name.bc > /dev/null
```
Now, the number of basic blocks in the program should be displayed.

###Note
The `opt` command comes with llvm, so make sure the llvm is correctly downloaded and installed.
Also note that the running of the LLVMCounter.dylib or LLVMCounter.so is independent of the environment once it is created.


## Authors

Rory(Qianyi Shu)

