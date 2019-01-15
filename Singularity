BootStrap: docker
From: nvidia/cuda:9.1-runtime-ubuntu16.04

%runscript
    echo "This is what happens when you run the container..."

%post
    apt-get update
    apt-get install -y --no-install-recommends \
    build-essential \
    apt-utils
    gcc-multilib \
    wget \
    unzip \
    python-dev \
    python3-dev \
    python-pip \
    python3-pip \
    pkg-config \
    python-setuptools \
    python3-setuptools
    
    mkdir -p /storage/home
    mkdir -p /storage/work
    mkdir -p /gpfs/scratch
    mkdir -p /gpfs/group
    
    cd /gpfs/scratch/
    wget https://www.mpipz.mpg.de/4607782/MGX-1_0_1280-LinuxMint18_1-CellAtlas-Cuda9_1.zip
    unzip MGX-1_0_1280-LinuxMint18_1-CellAtlas-Cuda9_1.zip
    dpkg -i MGX-1.0.1280-LinuxMint18.1-Cuda9.1-CellAtlas.deb
    apt-get install -y -f
    
    rm MGX-1_0_1280-LinuxMint18_1-CellAtlas-Cuda9_1.zip
    rm MGX-1.0.1280-LinuxMint18.1-Cuda9.1-CellAtlas.deb
    
    apt-get update
