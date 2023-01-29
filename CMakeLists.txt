cmake_minimum_required(VERSION 3.22.1)
project(sqlite3pp)

set(CMAKE_CXX_STANDARD 11)

#add_subdirectory(sqlite3)
add_library(sqlite3pp sqlite3/sqlite3.c sqlite3/sqlite3.h
 headeronly_src/sqlite3pp.h
 headeronly_src/sqlite3pp.ipp
)

set_target_properties(sqlite3pp PROPERTIES LINKER_LANGUAGE CXX)
target_include_directories(sqlite3pp PUBLIC sqlite3/sqlite3.h headeronly_src/sqlite3pp.h)
#set_target_properties(sqlite3pp sqlite3
#        PROPERTIES
#        PUBLIC_HEADER sqlite3/sqlite3.h
#        )


