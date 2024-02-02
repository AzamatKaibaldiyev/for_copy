# for_copy
```markdown
'git clone https://gitlab.freedesktop.org/mesa/mesa.git \
  && cd  /mesa \
  && mkdir build\
  && cd build \
  && meson --buildtype=release -Dprefix=/usr/local -Dglvnd=false -Dgallium-nine=false -Dgallium-omx=disabled -Dgallium-opencl=disabled -Dgallium-va=false -Dgallium-vdpau=false -Dgallium-xa=false -Dgallium-xvmc=false -Dvulkan-drivers= -Dglx=gallium-xlib -Degl=false -Dgbm=false -Dopengl=true -Dgles1=false -Dgles2=false -Dosmesa=true -Dshared-glapi=true -Dllvm=true -Dswr-arches=avx2 -Dplatforms=x11 -Dgallium-drivers=swrast,swr -Ddri-drivers= ..\
  && ninja install \
  && rm -rf /mesa'

################################

# Install build dependencies
sudo apt-get install -y build-essential

# Download CMake source code
wget https://cmake.org/files/v3.24/cmake-3.24.0.tar.gz

tar -xzvf cmake-3.24.0.tar.gz

cd cmake-3.24.0

# Build and install
./bootstrap

make

sudo make install

#########################

apt install dirmngr

apt-key adv --recv-keys EFDC8610341D9410 4CDB129629A4B41A 32B18A1260D8DA0B

apt-key --keyring /etc/apt/trusted.gpg list

########################
sudo apt-get build-dep libavresample

sudo apt-get install libavresample-doc

sudo apt-get source libavresample

cd libavresample-<version>

dpkg-buildpackage -uc -us

########################


sudo apt-get update
sudo apt-get install build-essential cmake git libgtk2.0-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev
sudo apt-get install libtbb2 libtbb-dev libjpeg-dev libpng-dev libtiff-dev libdc1394-22-dev


git clone https://github.com/opencv/opencv.git
cd opencv

git clone https://github.com/opencv/opencv_contrib.git
cd opencv_contrib


cd ../opencv
mkdir build
cd build

cmake -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/usr/local \
      -D OPENCV_EXTRA_MODULES_PATH=../../opencv_contrib/modules ..


make -j4  # Adjust the number according to the available CPU cores
sudo make install


python3 -c "import cv2; print(cv2.__version__)"
