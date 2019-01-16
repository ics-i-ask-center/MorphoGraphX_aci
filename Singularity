BootStrap: docker
From: nvidia/cuda:9.1-devel-ubuntu16.04

%runscript
    echo "This is what happens when you run the container..."

%post
    apt-get update
    apt-get install -y --no-install-recommends \
    build-essential \
    apt-utils \
    gcc-multilib \
    wget \
    unzip \
    python-dev \
    python3-dev \
    python-pip \
    python3-pip \
    pkg-config \
    python-setuptools \
    python3-setuptools \
    libqt4-dev \
    libqt4-opengl-dev \
    libglew-dev \
    cimg-dev \
    libgsl0-dev \
    libtiff5-dev \
    cmake \
    cmake-gui \
    doxygen
    
    # install nvidia driver (current system version: 390.30)
    add-apt-repository ppa:graphics-drivers/ppa
    apt install -y nvidia-390.30

    
    mkdir -p /storage/home
    mkdir -p /storage/work
    mkdir -p /gpfs/scratch
    mkdir -p /gpfs/group
    
    apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y locales
    
    cd /gpfs/scratch/
    
    wget https://www.mpipz.mpg.de/4607782/MGX-1_0_1280-LinuxMint18_1-CellAtlas-Cuda9_1.zip
    unzip MGX-1_0_1280-LinuxMint18_1-CellAtlas-Cuda9_1.zip
    dpkg -i MGX-1.0.1280-LinuxMint18.1-Cuda9.1-CellAtlas.deb || true
    apt-get install -y -f

    
    rm MGX-1_0_1280-LinuxMint18_1-CellAtlas-Cuda9_1.zip
    rm MGX-1.0.1280-LinuxMint18.1-Cuda9.1-CellAtlas.deb
    
