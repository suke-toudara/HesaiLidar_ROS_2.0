FROM osrf/ros:noetic-desktop-full

# Install dependencies
RUN \
  rm -rf /etc/apt/sources.list.d/ros1-latest.list && \
  apt-get update -q && \
  apt-get install -yq --no-install-recommends curl && \
  curl -sS https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg && \
  apt-key del C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654 && \
  echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros/ubuntu $( . /etc/os-release && echo $UBUNTU_CODENAME ) main" > /etc/apt/sources.list.d/ros1-latest.list && \
  rm -rf /var/lib/apt/lists/*

  
RUN apt-get update && apt-get install -y \
git \
cmake \
vim \
build-essential \
libboost-all-dev \
libyaml-cpp-dev \
&& rm -rf /var/lib/apt/lists/*
    
RUN mkdir -p /catkin_ws/src/HesaiLidar_ROS_2.0
RUN apt-get install -y libboost-all-dev \
    libyaml-cpp-dev 
WORKDIR /catkin_ws

# Create workspace