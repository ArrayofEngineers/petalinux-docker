# petalinux-docker

install docker, docker desktop works well ([here](https://www.docker.com/products/docker-desktop))

download petalinux-v2018.3-final-installer.run [here](https://www.xilinx.com/member/forms/download/xef.html?filename=petalinux-v2018.3-final-installer.run)

Copy petalinux-v2020.2-final-installer.run file to this folder. Then run:

`docker build --build-arg PETA_VERSION=2018.3 --build-arg PETA_RUN_FILE=petalinux-v2018.3-final-installer.run -t petalinux:2018.3 .`

After installation, launch petalinux with:

`docker run -ti --rm -e DISPLAY=$DISPLAY --net="host" -v /tmp/.X11-unix:/tmp/.X11-unix -v $HOME/.Xauthority:/home/vivado/.Xauthority -v $HOME/Projects:/home/vivado/project  petalinux:2018.3 /bin/bash`

OR

launch through docker desktop
