cmake_minimum_required(VERSION 3.1)

project(Textcat)

set(CMAKE_CXX_STANDARD 11)

if(CMAKE_CXX_COMPILER_ID MATCHES "GNU")
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wextra")
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -DNDEBUG -Ofast")
endif()

include_directories("include")

set(EXAMPLE_XML
    SAXReader
    SAXWriter
    DOMReader
    DOMWriter)

foreach(example ${EXAMPLE_XML})
    add_executable(XML_${example} example/XML/${example}/${example}.cpp)
endforeach()
