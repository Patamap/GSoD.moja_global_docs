.. _prerequisites:

Vcpkg Installation
##################

This section guides on the download and installation of Cmake as a prerequisite for FLINT on Windows.A fork of the original Vcpkg package has been created under moja global for the FLINT required libraries.

To build the libraries please follow the following steps:

* Clone the Vcpkg repository: https://github.com/moja-global/vcpkg

* Start a command shell in the Vcpkg repository folder and use the following commands:
::

    # bootstrap
    bootstrap-vcpkg.bat

    # install packages
    vcpkg.exe install boost-test:x64-windows boost-program-options:x64-windows boost-log:x64-windows turtle:x64-windows zipper:x64-windows poco:x64-windows libpq:x64-windows gdal:x64-windows sqlite3:x64-windows boost-ublas:x64-windows

* Once this has completed, start a command shell in your FLINT repository folder. Now use the following commands to create the Visual Studio solution:
::

    # Create a build folder under the Source folder
    cd Source
    mkdir build
    cd build

    # now create the Visual Studio Solution (2019)
    cmake -G "Visual Studio 16 2019" -DCMAKE_INSTALL_PREFIX=C:/Development/Software/moja -DVCPKG_TARGET_TRIPLET=x64-windows -DENABLE_TESTS=OFF -DENABLE_MOJA.MODULES.ZIPPER=OFF -DCMAKE_TOOLCHAIN_FILE=c:\Development\moja-global\vcpkg\scripts\buildsystems\vcpkg.cmake ..

    # OR Visual Studio Solution (2017)
    cmake -G "Visual Studio 15 2017" -DCMAKE_INSTALL_PREFIX=C:/Development/Software/moja -DVCPKG_TARGET
