# PCL 1.9.1

## Building PCL
### Prerequisites
```
sudo apt install checkinstall
```
### Instructions 
1. cd into the ```pcl-pcl-1.9.1``` directory and locate the CMakeLists.txt file.

2. Locate the find package(VTK) line (close to line 362) and edit it to find_package(VTK 7.1 REQUIRED)

3. Configure the build using the ccmake gui
```
mkdir build
cd build
ccmake ..
```
Then locate the BUILD_surface_on_nurbs flag and set it to ON

4. Build
```
make
```
Wait until the build finishes, it may take a couple of hours ...

5. Install
```
sudo checkinstall --pkgname=pcl-1.9.1
```
The installation process will prompt you to accept/reject some options prior to building the debian, just follow the recommended prompts

NOTE: Using checkinstall instead of make install has the advantage that it builds a debian package which can be easily uninstalled with sudo dpkg -r [packagename].
