# client-cpp
Client in language C++ for Apache IoTDB using CMake on Linux

# 0. Apache IoTDB:
* [Apache IoTDB website](http://iotdb.apache.org/)

* [Apache IoTDB github](https://github.com/apache/incubator-iotdb)

# 1. Description of project structure
* SessionExample.cpp : the main function of the project, containing examples of the client methods to use IoTDB
* Session (folder) : Class Session which wrap the rpc interfaces generated by thrift
* gen-cpp (folder) : the cpp files generated by thrift from rpc.thrift and sync.thrift
* CMakeLists.txt (the one under project root directory) : the CMakeLists for the whole project
* build (folder) : the files generated by cmake while compiling and after compiled. The final executable file client-cpp is in it.
* libthrift.a, libthriftnb.a : thrift cpp static library

# 2. How to run
Under the project root directory, run commands:
```
cd build

cmake ..

make

./client-cpp
```

# 3. Possible improvements
If write a .sh or .bat shell file to make the progress automatically, then the gen-cpp folder is not needed.

The sript file can be coded following steps below:

step 1: Using thrift to compile rpc.thrift and sync.thrift, get gen-cpp folder.

step 2: Delete TSIService_server.skeleton.cpp and SyncService_server.skeleton.cpp in gen-cpp folder

step 3: run command: cmake .. , make, ./client-cpp successively under the client-cpp/build

# 4. More info
* thrift version: 0.13.0
* Apache IoTDB version: apache-iotdb-0.10.0
* If you want to use the own thrift cpp liarary, just change the CMakeLists.txt.
