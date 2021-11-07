# curl-msvc
## Infomation
curl cmake module libcurl build with MSVC10.0 arch (x86 | i386)

source from https://github.com/curl/curl  tags: curl-7_79_1

## Usage in cmake
Put the libcurl/ folder to the project path with the CMakeLists.txt file

Add the following command to the CMakeLists.txt file

```CMake
set(CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}
  ${CMAKE_CURRENT_SOURCE_DIR}/libcurl/cmake
)

find_package(LIBCURL REQUIRED)
```
Check the variable LIBCURL_FOUNDED to determine whether the LIBCURL was imported successful

```CMake
if(LIBCURL_FOUNDED)
    message(STATUS "libcurl founded: " ${LIBCURL_LIBRARY})
    include_directories(${LIBCURL_INCLUDE_DIR})
    link_directories(${LIBCURL_LIBRARY})
else()
    message(STATUS "!!!! libcurl not found !!!!")
endif()
````

