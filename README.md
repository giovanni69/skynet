# skynet
Installing skynet on Ubuntu Desktop 21.10

Sources:
https://bitbucket.org/jlippuner/skynet/src/master/

sudo apt install git
sudo apt install cmake
sudo apt install gfortran
sudo apt install build-essential
sudo apt install libhdf5-dev
sudo apt install swig4.0
sudo apt install libpython-all-dev
sudo apt install libpython3-all-dev
sudo apt install libgsl-dev
sudo apt install libboost-all-dev
sudo apt install libfreetype6-dev
sudo apt install libcairo2-dev
sudo apt install libcairomm-1.0-dev
sudo apt install libsigc++-2.0-dev
sudo apt install ffmpeg
sudo apt install libmkl-full-dev

cd Scrivania
mkdir skynet_install
git clone https://bitbucket.org/jlippuner/skynet.git
cd skynet
mkdir build
cd build

cmake -DSKYNET_MATRIX_SOLVER=mkl \
      -DCMAKE_INSTALL_PREFIX=/home/luca/Scrivania/skynet_install \
      -DMKL_LIBRARY_DIR=/usr/lib/x86_64-linux-gnu \
      -DMKL_INCLUDE_DIRS=/usr/include/mkl \
      -DMKL_LIBRARIES=/usr/lib/x86_64-linux-gnu ..
      
make -j4 install

make test
