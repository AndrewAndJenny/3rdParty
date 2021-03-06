# 3rdParty

a depository which contains some libraries used for LiDARpro
all build packages under ubuntu 18.04

## List

the libraries of this depository as follows:
* LASlib
* PCL-1.8.0
* Opencv+contrib-3.4.3
* CGAL(version 4/5)
* Qt5-5.9.5 + Qt5-svg
* GDAL-2.2.3
* cere-1.14
* pdal-1.6.0

* OpenGL
* glew
* glut
* tbb
* openmp


##  Usage

```
git clone https://github.com/AndrewAndJenny/3rdParty.git
```



## LASlib

1.1 one method is that we copy library into **/usr/local**
```
cd 3rdParty/LAS
sudo cp -r include/* /usr/local/inlcude
sudo cp -r lib/* /usr/local/lib
```
the second method is that we add the path of **3rdParty/lib**,**3rdParty/include** into [envionment variables](https://blog.csdn.net/u011976443/article/details/86631653)



## PCL

```
sudo apt install libpcl-dev
```

**pcl include a list of 3rdParty**
```
eigin(sudo apt install libeigin3-dev)
boost(sudo apt install libboost-all-dev(1.58.0.1))
vtk
flann
OpenNI2
Qhull
```

**notice**

if you want compile the CGAL5.0.0,you should build boost version of 1.66 and more. 

## Opencv+contrib

* 3.1 if you just use opencv, not use contrib:
```
sudo apt-get install libopencv-dev
```

* if you use [opencv+contirb](https://blog.csdn.net/qq_36486890/article/details/97511295):  

3.1 Start by installing all the dependencies

```
sudo apt install  build-essential
sudo apt install cmake git libgtk2.0-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev  
sudo apt install python-dev python-numpy libtbb2 libtbb-dev libjpeg-dev libpng-dev libtiff-dev libjasper-dev libdc1394-22-dev
```
if can't insatll libjasper-dev
```
sudo add-apt-repository "deb http://security.ubuntu.com/ubuntu xenial-security main"
sudo apt update
sudo apt upgrade
sudo apt install libjasper1 libjasper-dev
```

3.2 decompression the opencv of 3rdparty and copy it to /usr/local/

3.3 must be **attention**!!!
if we copy .so files to /usr/local/lib,we must use **cp -d**command to protect the **Symbolic link**



## CGAL

* 4.1 an easy method is that use command line(cgal-4):
```
sudo apt-get install libcgal-dev
apt-get install libcgal-demo
```

* 5.0.0 [source code build](https://blog.csdn.net/miscclp/article/details/44087749)

Start by installing all the dependency
```
sudo apt-get install libgmp-dev libmpfr-dev
```

4.2 decompression the CGAL of 3rdparty and copy it to /usr/local/



## Qt5

```
sudo apt-get install qt-default
```



## GDAL

```
sudo apt-get install libgdal-dev gdal-bin
```

if occur

```
undefined reference to `sqlite3_column_origin_name'
undefined reference to `sqlite3_column_table_name'
```

Please co-compile [sqlite3](https://www.cnblogs.com/xuanmanstein/p/13227545.html)

## vcglib

```
decompression the vcglib of 3rdparty and copy it
```



## cere

8.1 Start by installing all the [dependencies](http://ceres-solver.org/installation.html)

```
# CMake
sudo apt-get install cmake
# google-glog + gflags
sudo apt-get install libgoogle-glog-dev libgflags-dev
# BLAS & LAPACK
sudo apt-get install libatlas-base-dev
# Eigen3
sudo apt-get install libeigen3-dev
# SuiteSparse and CXSparse (optional)
sudo apt-get install libsuitesparse-dev
```

Notes:

* if we install **PCL** and **CMake**,we needn't install repeately. 

* The cere2.0.0 version is very advanced ,so we **go back** to **cere1.14.0**
* cere1.14.0 need **eigen3.2.x**,and this version must not have BLAS、LAPACK、SuiteSparse and CXSparse

8.2 decompression the cere of 3rdparty and copy it to /usr/local/



##  [pdal](https://launchpad.net/ubuntu/+source/pdal)

```
sudo apt get-install libpdal-dev
```



## OpenGL

```
sudo apt-get install build-essential libgl1-mesa-dev
sudo apt-get install freeglut3-dev
sudo apt-get install libglew-dev libsdl2-dev libsdl2-image-dev libglm-dev libfreetype6-dev
```



## configure bash

I think if we use CMake to build project by ourselves, don't need do it:smile_cat:

```
sudo gedit /etc/bash.bashrc  

Add at the end:
PKG_CONFIG_PATH=$PKG_CONFIG_PATH:/usr/local/lib/pkgconfig  
export PKG_CONFIG_PATH

Save and commad:
source /etc/bash.bashrc

Upadate:
sudo updatedb
```

If you found bugs or have new ideas,please pull requests:smile:  
If you have trouble compiling or using this software,email to 15313326374@163.com

## Good Luck For You!
