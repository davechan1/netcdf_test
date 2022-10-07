# netcdf_test
 netcdf c++ library from [example](https://github.com/Unidata/netcdf-cxx4/tree/master/examples), just wrapped with CMake. Nothing special.

install (in Ubuntu 20.04)
``` 
sudo apt-get install libnetcdf-dev
sudo apt-get install libnetcdf-c++4-dev
```

in ~/.bashrc add to LD_LIBRARY_PATH:
```
LD_LIBRARY_PATH=/usr/local/lib:$LD_LIBRARY_PATH; export LD_LIBRARY_PATH
```

using g++:
```
g++ simple_xy_wr.cpp -lnetcdf_c++4 -lnetcdf
```

using CMake:
```
mkdir build 
cd build 
cmake ..
make
```
