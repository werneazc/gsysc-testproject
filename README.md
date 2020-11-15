# Small Test Project to Test gSysC Library

## Dependencies

  + SystemC 2.3.2
  + gSysC
  + Qt4

## Arrangements

Please add the following Variables to your environment

``` sh
EXPORT SYSTEMC_ROOT=<Path to SystemC root directory>
EXPORT GSYSC_ROOT=<Path to GsysC root directory>
```

In `cmake/modules` , the find scripts will search for the necessary libaries and include directories.

The compilation's success depence on the right C++ standard set. It needs to fit to the standard you had used to compile your SystemC. 
You can change the standard in CMakeLists.txt with the option `target_compile_features(gsysc_testproject PRIVATE cxx_std_14)` . 

## Build

``` sh
mkdir ./build && cd ./build
cmake ../
make gsysc_testproject
```
