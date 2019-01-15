BootStrap: docker
#From: nvidia/cuda:9.1-devel-ubuntu16.04
From: nvidia/cuda:9.0-devel-ubuntu16.04

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
    
    mkdir -p /storage/home
    mkdir -p /storage/work
    mkdir -p /gpfs/scratch
    mkdir -p /gpfs/group
    
    apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y locales
    
    cd /gpfs/scratch/
#    wget https://www.mpipz.mpg.de/4607782/MGX-1_0_1280-LinuxMint18_1-CellAtlas-Cuda9_1.zip
#    unzip MGX-1_0_1280-LinuxMint18_1-CellAtlas-Cuda9_1.zip
#    dpkg -i MGX-1.0.1280-LinuxMint18.1-Cuda9.1-CellAtlas.deb || true
#    apt-get install -y -f

# On ACI cluster, current driver version (390.30) does not support CUDA toolkit 9.1
# So, try to download 9.0 version of MGX
# https://docs.nvidia.com/deploy/cuda-compatibility/index.html
    wget https://www.mpipz.mpg.de/4607782/MGX-1_0_1280-LinuxMint18_1-CellAtlas-Cuda9_0.zip
    unzip MGX-1_0_1280-LinuxMint18_1-CellAtlas-Cuda9_0.zip
    # They don't seem like to support 9.0 version (output has same name)
    dpkg -i MGX-1.0.1280-LinuxMint18.1-Cuda9.1-CellAtlas.deb || true
    
    rm MGX-1_0_1280-LinuxMint18_1-CellAtlas-Cuda9_1.zip
    rm MGX-1.0.1280-LinuxMint18.1-Cuda9.1-CellAtlas.deb
    
