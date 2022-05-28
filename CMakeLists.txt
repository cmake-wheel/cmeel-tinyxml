cmake_minimum_required(VERSION 3.1)

project(cmeel-tinyxml)

set(tinyxml_SOURCES
  tinyxml/tinyxml.cpp
  tinyxml/tinyxmlerror.cpp
  tinyxml/tinyxmlparser.cpp)

set(tinyxml_HEADERS
  tinyxml/tinyxml.h
  tinyxml/tinystr.h)

add_library(tinyxml SHARED ${tinyxml_SOURCES} ${tinyxml_HEADERS})
target_include_directories(tinyxml PUBLIC $<INSTALL_INTERFACE:include>)
target_compile_definitions(tinyxml PUBLIC -DTIXML_USE_STL)

install(TARGETS tinyxml LIBRARY DESTINATION lib)
install(FILES ${tinyxml_HEADERS} DESTINATION include)
