# netcdf_test
 netcdf c++ library
``` 
sudo apt-get install libnetcdf-dev
sudo apt-get install libnetcdf-c++4-dev
```

in ~/.bashrc:
```
LD_LIBRARY_PATH=/usr/local/lib:$LD_LIBRARY_PATH; export LD_LIBRARY_PATH
```

g++:
```
g++ simple_xy_wr.cpp -lnetcdf_c++4 -lnetcdf
```

CMake:
```
mkdir build 
cd build 
cmake ..
make
```
