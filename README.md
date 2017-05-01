# Honeyd using docker

# BASIS
* Seems to work on debian 3.16.0-4
https://github.com/DataSoft/Honeyd

# Setup
sudo apt-get install libevent-dev libdumbnet-dev libpcap-dev libpcre3-dev libedit-dev bison flex libtool automake
./autogen.sh
./configure
make
sudo make install

# Docker installation (Debian)
https://docs.docker.com/engine/installation/linux/debian/#install-using-the-repository

# Docker bild
sudo docker build -t <name> <folder>

# Running docker:
sudo docker run -p yourport:80 <name>

# 
