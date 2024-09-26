# Getting started with GraalVM 

This helloworld project introduce you to GraalVM Native Technology 


## Setup 

Download and install [GraalVM](oracle.com/graalvm) 
```
$ sdk install java 23-graal
$ java version "23" 2024-09-17
Java(TM) SE Runtime Environment Oracle GraalVM 23+37.1 (build 23+37-jvmci-b01)
Java HotSpot(TM) 64-Bit Server VM Oracle GraalVM 23+37.1 (build 23+37-jvmci-b01, mixed mode, sharing)
```

## Build application 
``$ mvn clean package 
``

``` 
$ native-image -cp target/*.jar  com.oracle.graalvm.App MyApp
=======================================================================================================================
GraalVM Native Image: Generating 'MyApp' (executable)...
========================================================================================================================
[1/8] Initializing...                                                                                    (3,7s @ 0,17GB)
 Java version: 23+37, vendor version: Oracle GraalVM 23+37.1
 Graal compiler: optimization level: 2, target machine: armv8-a, PGO: ML-inferred
 C compiler: cc (apple, arm64, 15.0.0)
 Garbage collector: Serial GC (max heap size: 80% of RAM)
 1 user-specific feature(s):
 - com.oracle.svm.thirdparty.gson.GsonFeature
------------------------------------------------------------------------------------------------------------------------
Build resources:
 - 26,49GB of memory (73,6% of 36,00GB system memory, determined at start)
 - 11 thread(s) (100,0% of 11 available processor(s), determined at start)
[2/8] Performing analysis...  [*****]                                                                    (2,6s @ 0,19GB)
    1 985 reachable types   (57,5% of    3 452 total)
    1 769 reachable fields  (38,2% of    4 631 total)
    8 548 reachable methods (35,2% of   24 316 total)
      730 types,     7 fields, and    90 methods registered for reflection
       49 types,    33 fields, and    48 methods registered for JNI access
        4 native libraries: -framework Foundation, dl, pthread, z
[3/8] Building universe...                                                                               (0,4s @ 0,24GB)
[4/8] Parsing methods...      [*]                                                                        (0,7s @ 0,24GB)
[5/8] Inlining methods...     [***]                                                                      (0,5s @ 0,29GB)
[6/8] Compiling methods...    [***]                                                                      (6,5s @ 0,39GB)
[7/8] Laying out methods...   [*]                                                                        (0,7s @ 0,24GB)
[8/8] Creating image...       [*]                                                                        (0,6s @ 0,30GB)
   2,83MB (44,16%) for code area:     3 861 compilation units
   3,38MB (52,73%) for image heap:   52 735 objects and 86 resources
 203,65kB ( 3,11%) for other data
   6,40MB in total
```

## Run the application 
```shell 
$ ./MyApp 
Hello World!
```
