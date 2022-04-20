FROM osrf/ros:rolling-desktop-focal

# ** [Optional] Uncomment this section to install additional packages. **
#
ENV DEBIAN_FRONTEND=noninteractive

# Install language
RUN apt-get update && apt-get install -y \
  locales \
  && locale-gen en_US.UTF-8 \
  && update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8 \
  && rm -rf /var/lib/apt/lists/*
ENV LANG en_US.UTF-8

RUN dpkg --add-architecture i386
RUN apt-get update \
   && apt-get -y install --no-install-recommends \
   libtinfo5 \
   libxtst6 \
   lib32stdc++6 \
   libgtk2.0-0:i386 \
   libfontconfig1:i386 \
   libx11-6:i386  \
   libxext6:i386 \
   libxrender1:i386 \
   libsm6:i386 \
   libxtst6:i386 \
   curl \
   build-essential \
   libssl-dev \
   git \
   wget \
   ocl-icd-* \
   opencl-headers \
   python3-vcstool \
   python3-colcon-common-extensions \
   python3-colcon-mixin \
   kpartx \
   gdisk \
   parted \
   cpio \
   dosfstools \
   u-boot-tools \
   pv \
   libgazebo11-dev \
   libidn11 \
   #
   # Clean up
   && apt-get autoremove -y \
   && apt-get clean -y \
   && rm -rf /var/lib/apt/lists/*

ENV DEBIAN_FRONTEND=dialog

# Set up auto-source of workspace for ros user
# ARG WORKSPACE
# RUN echo "if [ -f ${WORKSPACE}/install/setup.bash ]; then source ${WORKSPACE}/install/setup.bash; fi" >> /home/ros/.bashrc
# RUN source /tools/Xilinx/Vitis/2021.2/settings64.sh
# RUN source /opt/ros/rolling/setup.bash