# graalvm-helloworld-nativeimage
Basic project to showcase natige image build 
GraalVM Native Image Helloworld Maven project 

## Setup 

Download and install [GraalVM](oracle.com/graalvm) + native image`  extension
```
> `export GRAALVM_HOME=~/Applications/Java/graalvm-ce-java11-20.3.0/Contents/Home`
> export JAVA_HOME=$GRAALVM_HOME
> $GRAALVM_HOME/bin/gu install native-image
```

## Build application 
``$ mvn clean package 
``

``` 
$ $GRAALVM_HOME/bin/native-image -cp target/*.jar  com.oracle.graalvm.demos.hellonative.App MyApp
[MyApp:40125]    classlist:   1,289.97 ms,  0.96 GB
[MyApp:40125]        (cap):   3,822.10 ms,  0.96 GB
[MyApp:40125]        setup:   4,968.84 ms,  0.96 GB
[MyApp:40125]     (clinit):     187.69 ms,  1.22 GB
[MyApp:40125]   (typeflow):   4,627.57 ms,  1.22 GB
[MyApp:40125]    (objects):   3,777.57 ms,  1.22 GB
[MyApp:40125]   (features):     215.59 ms,  1.22 GB
[MyApp:40125]     analysis:   8,982.80 ms,  1.22 GB
[MyApp:40125]     universe:     370.63 ms,  1.22 GB
[MyApp:40125]      (parse):   1,138.75 ms,  1.22 GB
[MyApp:40125]     (inline):   1,464.16 ms,  1.67 GB
[MyApp:40125]    (compile):   7,681.46 ms,  2.28 GB
[MyApp:40125]      compile:  10,796.54 ms,  2.28 GB
[MyApp:40125]        image:   1,434.97 ms,  2.28 GB
[MyApp:40125]        write:     399.10 ms,  2.28 GB
[MyApp:40125]      [total]:  28,405.18 ms,  2.28 GB

```


## Run the application 
```shell 
$ ./MyApp 
Hello World!
```
