# client-cpp
Client in language C++ for Apache IoTDB using CMake on Linux

# 0. Apache IoTDB:
* [Apache IoTDB website](http://iotdb.apache.org/)

* [Apache IoTDB github](https://github.com/apache/incubator-iotdb)

# 1. Description of client-cpp structure
* `SessionExample.cpp` : the main function of the project, containing examples of the client methods to use IoTDB 
* `compile.sh` : The script to compile the client automatically.
* `Session` (folder) : Class Session which wrap the rpc interfaces generated by thrift
* `CMakeLists.txt` (the one under project root directory) : the CMakeLists for the whole project
* `build` (folder) : The files generated by cmake while compiling and after compiled. Before compiling, this folder is empty.
* `libthrift.a, libthriftnb.a` : thrift cpp static library

# 2. How to run
Under the project root directory, run commands:
```
./chmod u+x compile.sh

./compile.sh

./client-cpp
```

# 3. Prerequisites
* thrift version: 0.13.0 : you need to build and install thrift out of the source repository, just refer to this website:[Building Thrift from source](https://thrift.apache.org/docs/BuildingFromSource). You may note that after this by default the thrift C++ library(both static and dynamic) is built already, you can find them in the lib/cpp/.lib folder.
* cmake version: 3.16 : [CMake Download](https://cmake.org/download/)

# 4. Example
We provided an example of how to use the thrift library to connect to IoTDB in client-cpp/SessionExample.cpp, please read it carefully before you write your own code

# 5 More Info
## 5.1 Compile related problems
* If you have added Thrift executable into your path, you can run client-cpp/compile.sh directly, or you have to modify it to set variable `THREFT_EXE` to point to your executable. This will generate gen-cpp folder automatically.

* If you want to use your own thrift cpp library, just change the CMakeLists.txt.(that is to say, if you run this project on Windows system, you need change the thrift cpp static library to .lib library file)
