# Make biolib_ruby_rqtl module

cmake_minimum_required(VERSION 2.6)
ENABLE_TESTING()

SET (M_NAME rqtl)
# SET (M_VERSION 1.11.6)
SET (INTERFACE ruby_${M_NAME}.i)

IF(NOT BUILD_LIBS)
  SET (CMAKE_MODULE_PATH ../../../../../cmake_modules)
ENDIF(NOT BUILD_LIBS)

SET (USE_ZLIB TRUE)
SET (USE_RLIB TRUE)
# SET (USE_INCLUDEPATH io_lib)

INCLUDE(CMakeBackwardCompatibilityC)
SET(CMAKE_LIBRARY_OUTPUT_DIRECTORY biolib)

FIND_PACKAGE(BioLibRuby)

ADD_TEST(TestRubyRQTLLib ${RUBY_EXECUTABLE} -I../${M_NAME} ./../test/test_${M_NAME}.rb)

INSTALL(TARGETS ${M_MODULE}
  LIBRARY DESTINATION ${RUBY_LIB_PATH}/biolib
)


