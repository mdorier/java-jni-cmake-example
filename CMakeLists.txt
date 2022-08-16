cmake_minimum_required (VERSION 3.0)
project (HelloWorld)

find_package (Java REQUIRED)
include (UseJava)

set (JAR_NAME HelloWorld ENTRY_POINT HelloWorld)
set (JAVA_SOURCE_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/java)
set (JAVA_SOURCE_FILES ${JAVA_SOURCE_DIRECTORY}/HelloWorld.java)
add_jar (${JAR_NAME} ${JAVA_SOURCE_FILES})
