# for_copy



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
