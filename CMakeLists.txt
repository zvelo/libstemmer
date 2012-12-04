CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

PROJECT(libstemmer)

FILE(GLOB SNOWBALL_SOURCES
  src_c/*.c
  runtime/api.c
  runtime/utilities.c
  libstemmer/libstemmer.c
)

ADD_LIBRARY(stemmer SHARED ${SNOWBALL_SOURCES})
ADD_LIBRARY(stemmer-static STATIC ${SNOWBALL_SOURCES})
SET_TARGET_PROPERTIES(stemmer-static PROPERTIES OUTPUT_NAME "stemmer")

INSTALL(TARGETS stemmer stemmer-static DESTINATION lib)
INSTALL(FILES include/libstemmer.h DESTINATION include)
