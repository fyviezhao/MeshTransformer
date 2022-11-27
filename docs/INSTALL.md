## Installation

Our codebase is developed based on Ubuntu 16.04 and NVIDIA GPU cards. 

### Requirements
- Python 3.7
- Pytorch 1.4
- torchvision 0.5.0
- cuda 10.1

### Setup with Conda

We suggest to create a new conda environment and install all the relevant dependencies. 

```bash
# Create a new environment
conda create --name metro python=3.8
conda activate metro

# Clone METRO
git clone --recursive https://github.com/fyviezhao/MeshTransformer.git
cd MeshTransformer
export INSTALL_DIR=$PWD

# Install Pytorch
conda install pytorch==1.10.0 torchvision==0.11.0 torchaudio==0.10.0 cudatoolkit=11.3 -c pytorch -c conda-forge

# Install apex
cd $INSTALL_DIR
git clone https://github.com/NVIDIA/apex.git
conda install -c conda-forge packaging
cd apex
python setup.py install --cuda_ext --cpp_ext

# Install OpenDR pre-requests
sudo apt install libosmesa6-dev
sudo apt-get install build-essential
sudo apt-get install libgl1-mesa-dev
sudo apt-get install libglu1-mesa-dev
sudo apt-get install freeglut3-dev

# Install OpenDR
pip install opendr matplotlib

# Install METRO
cd $INSTALL_DIR
python setup.py build develop

# Install requirements
pip install -r requirements.txt

# Install manopth
cd $INSTALL_DIR
pip install ./manopth/.

unset INSTALL_DIR
```


