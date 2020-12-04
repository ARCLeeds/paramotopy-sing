Bootstrap: docker
From: ubuntu:18.04

%post

######### download and install Bertini v1.6
apt-get update
apt-get install -yq openssh-server wget gnupg libmpfr-dev python \
                    build-essential libgmp3-dev bison libboost-all-dev \
                    libgmp3-dev mpich flex
wget https://bertini.nd.edu/BertiniSource_v1.6.tar.gz
tar -xzf BertiniSource_v1.6.tar.gz --no-same-owner
chmod -R 775 BertiniSource_v16

cd BertiniSource_v16
mkdir install
./configure --prefix=/BertiniSource_v16/install/
make
make install


%runscript

    exec "/BertiniSource_v16/install/bin/$@"