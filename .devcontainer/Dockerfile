FROM openjdk:17-slim
# SysML v2 Version
ARG RELEASE=2023-10
RUN apt-get --quiet --yes update && apt-get install -yqq \
  wget 

# Install MiniConda
RUN mkdir -p /home/root/miniconda3
RUN wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-$(uname -m).sh -O /home/root/miniconda3/miniconda.sh
RUN bash /home/root/miniconda3/miniconda.sh -b -u -p /home/root/miniconda3
RUN rm -rf /home/root/miniconda3/miniconda.sh

# Install Jupyter SysML
RUN mkdir -p /home/root/sysml
RUN wget -q https://github.com/Systems-Modeling/SysML-v2-Release/archive/refs/tags/${RELEASE}.tar.gz -O /home/root/sysml/${RELEASE}.tar.gz
RUN tar xzf /home/root/sysml/${RELEASE}.tar.gz -C /home/root/sysml
## This is the path that conda init setups but conda init has no effect
## here, so setup the PATH by hand. Else install.sh won't work.
## -> see, https://github.com/gorenje/sysmlv2-jupyter-docker/blob/main/Dockerfile
ENV PATH="/home/root/miniconda3/bin:/home/root/miniconda3/condabin:/usr/local/openjdk-17/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
WORKDIR /home/root/sysml/SysML-v2-Release-${RELEASE}/install/jupyter
RUN ./install.sh

CMD jupyter lab --allow-root