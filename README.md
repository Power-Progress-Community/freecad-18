FreeCAD 0.18.3
-------

Freecad 0.18.3 build with python 2.7 and QT4, optimized for PPC64be.

![screenshot](http://www.freecadweb.org/wiki/images/thumb/7/72/Freecad016_screenshot1.jpg/800px-Freecad016_screenshot1.jpg)

FreeCAD is a general purpose feature-based, parametric 3D modeler for 
CAD, MCAD, CAx, CAE and PLM, aimed directly at mechanical engineering 
and product design but also fits a wider range of uses in engineering, 
such as architecture or other engineering specialties. It is 100% Open 
Source (LGPL2+ license) and extremely modular, allowing for very 
advanced extension and customization.

FreeCAD is based on OpenCASCADE, a powerful geometry kernel, features an 
Open Inventor-compliant 3D scene representation model provided by the 
Coin 3D library, and a broad Python API. The interface is built with Qt. 
FreeCAD runs exactly the same way on Windows, Mac OSX, BSD and Linux 
platforms.

- [Home page](http://www.freecadweb.org)
- [Documentation wiki](http://www.freecadweb.org/wiki/)

Installing
----------

Precompiled packages with Altivec optimizations are available for PowerPC 64 Big Endian on our Repository 
[Releases page](https://repo.powerprogress.org/debian/buildpak/freecad-18/).

Building
---------

Compiling FreeCAD requires installation of several libraries and their 
development files such as OpenCASCADe, Coin and Qt, listed in the 
pages below. Once this is done, FreeCAD can be simply compiled with 
cMake. 

**Please note that not all develepment libraries are available on Debian repository **

the following deps are necessary to build :
+ cmake 
+ build-essential 
+ libtool 
+ lsb-release 
+ swig 
+ libboost-dev 
+ libboost-date-time-dev 
+ libboost-filesystem-dev 
+ libboost-graph-dev 
+ libboost-iostreams-dev 
+ libboost-program-options-dev 
+ libboost-python-dev 
+ libboost-regex-dev 
+ libboost-serialization-dev 
+ libboost-thread-dev 
+ libcoin-dev 
+ libeigen3-dev 
+ libgts-bin 
+ libgts-dev 
+ libkdtree++-dev 
+ libmedc-dev 
+ libopencv-dev 
+ libproj-dev 
+ libvtk6-dev 
+ libx11-dev 
+ libxerces-c-dev 
+ libzipios++-dev 
+ qt4-dev-tools 
+ libqt4-dev 
+ libqt4-opengl-dev 
+ libqtwebkit-dev 
+ libshiboken-dev 
+ libpyside-dev 
+ pyside-tools 
+ python-dev 
+ python-matplotlib 
+ python-ply 
+ python-pyside 
+ libocct*-dev 
+ occt-draw 
+ libsimage-dev 
+ doxygen 
+ libcoin-doc 
+ dh-exec 
+ libspnav-dev 

to build first clone this repository then<br> 
mkdir freecad-build<br>
cmake -DCMAKE_BUILD_TYPE=Release -DBUILD_QT5=OFF -DPYTHON_EXECUTABLE=/usr/bin/python2.7 -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 -DPYTHON_LIBRARY=/usr/lib/powerpc64-linux-gnu/libpython2.7.so -DPYTHON_PACKAGES_PATH=/usr/local/lib/python2.7/dist-packages/ --with-boost-libdir=/usr/local/include/boost/ ../freecad-18 <br>
make -j2<br>

Usage & Getting help
--------------------

For usage of FREECAD please refeer to Freecad main site [FreeCAD](https://www.freecadweb.org/)

Notes
-----
Locate the FreeCAD executable file (usually in /usr/lib/FreeCAD/bin)<br>
Execute the command 'ldd FreeCAD' from the terminal<br>
Write down the version of the libCoin.so library that FreeCAD is using (e.g. libCoin.so.60)<br>
Locate the libSoQt.so library (usually in /usr/lib)<br>
Execute 'ldd libSoQt.so' and check if it refers to the same version of Coin that FreeCAD refers to
If there are any differences, FreeCAD or SoQt must be recompiled. Best to recompile the one that uses the older version of Coin. It is best to try to contact the people responsible for packaging SoQt or FreeCAD and politely ask them to consider recompiling. If you want to undertake this task yourself, and you can't recompile SoQt because it will damage other applications on your system, you can force FreeCAD to compile with the required Coin version via ./configure --with-coin=DIR. But you have to make sure that the correct package of this Coin version is installed.
