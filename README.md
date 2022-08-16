# Java/JNI CMake example

This repository aims at illustrating how to integrate
Java with native C/C++ using CMake.

To build this project, make sure you have a Java SDK
(such as OpenJDK) installed. Make sure the `JAVA_HOME`
environment variable points to the location where this
SDK is installed, then proceed as follows.

```
mkdir build
cd build
cmake ..
make
```

This will build two jars. The first one, `HelloWorld.jar`,
only aims to show how to build a jar with cmake.
The second one, `HelloWordJNI.jar`, shows how to generate
a native header using cmake and how to build a native library
(`HelloWorld-cpp`) that can be used by Java.

Executing the first jar can be done as follows.

```
java -jar HelloWorld.jar
```

Executing the first jar can be done as follows.

```
LD_LIBRARY_PATH=$LD_LIBRARY_PATH:`pwd` java -jar HelloWorldJNI.jar
```

The `LD_LIBRARY_PATH` needs to point to the location of the
C++ `libHelloWorldJNI-cpp.so` that CMake has built.
