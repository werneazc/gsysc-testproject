cmake_minimum_required(VERSION "3.14")

project(
  gSyscTestProject
  VERSION "0.1.0"
  DESCRIPTION "Test project for GsysC")

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH}
                      ${CMAKE_CURRENT_SOURCE_DIR}/cmake/modules)

find_package(GsysC)
find_package(SystemC)
find_package(Qt4)

add_executable(
  gsysc_testproject gSysC_testproject/consumer.cc gSysC_testproject/fifo.cc
                    gSysC_testproject/producer.cc gSysC_testproject/main.cc)
target_compile_features(gsysc_testproject PRIVATE cxx_std_14)
target_link_libraries(
  gsysc_testproject PRIVATE ${GSYSC_LIBRARIES} ${SYSTEMC_LIBRARIES} Qt4::QtCore
                            Qt4::QtGui Qt4::Qt3Support "pthread")
target_include_directories(
  gsysc_testproject PRIVATE ${GSYSC_INCLUDE_DIRS} ${SYSTEMC_INCLUDE_DIRS}
                            ${CMAKE_CURRENT_SOURCE_DIR})
target_compile_definitions(gsysc_testproject PRIVATE SC_USE_SC_STRING_OLD)
