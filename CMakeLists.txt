CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

PROJECT(libstemmer)

FILE(GLOB SNOWBALL_SOURCES
  src_c/*.c
  runtime/api.c
  runtime/utilities.c
  libstemmer/libstemmer.c
)

ADD_LIBRARY(stemmer ${SNOWBALL_SOURCES})

INSTALL(TARGETS stemmer DESTINATION lib)
INSTALL(FILES include/libstemmer.h DESTINATION include)
