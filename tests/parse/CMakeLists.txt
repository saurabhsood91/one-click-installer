CMAKE_MINIMUM_REQUIRED(VERSION 2.8)
ENABLE_TESTING(TRUE)
find_package(Qt4 REQUIRED)
add_definitions(${QT_DEFINITIONS})
SET(${QT_USE_QTTEST} TRUE)
include(${QT_USE_FILE})
#include_directories("../../src/backend")
#set(PARSETEST_SRCS parsetest.cpp)
#QT4_AUTOMOC(${PARSETEST_SRCS})
ADD_EXECUTABLE(ParseTest parsetest.cpp YmpParser.cpp package.cpp repository.cpp)
TARGET_LINK_LIBRARIES(ParseTest ${QT_LIBRARIES} ${QT_QTTEST_LIBRARY} ${PARSETEST_SRCS})
ADD_TEST(NAME ParseTest COMMAND ParseTest)
