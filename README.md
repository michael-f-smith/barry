# barry

# Raspian Roomba

# Setting Static IP
https://www.makeuseof.com/raspberry-pi-set-static-ip/
```
sudo nano /etc/dhcpcd.conf

# At the bottom of the file, add the following (and replace):
interface NETWORK 
static ip_address=STATIC_IP/24
static routers=ROUTER_IP 
static domain_name_servers=DNS_IP
```


# Cameras
https://thepihut.com/blogs/raspberry-pi-tutorials/16021420-how-to-install-use-the-raspberry-pi-camera
```
# Use libcamera
# To capture a single picture:
libcamera-jpeg -o image.jpg

# vcgencmd
vcgencmd get_camera
```

# Install pip
```
sudo apt install python3-pip
```

# Install vcstools
```
sudo pip3 install vcstools
```

# Install git 
```
sudo apt install git
```
# Install colcon:
```
python3 -m pip install colcon-common-extensions
```

# Install ros deps:
```
sudo apt-get install python3-rosdep python3-rosinstall-generator build-essential
```

# Install libignition
```
sudo apt-get install libignition-math6-dev
```

# ROS2 Humble Install
https://docs.ros.org/en/humble/Installation/Alternatives/Ubuntu-Development-Setup.html
```
locale  # check for UTF-8

sudo apt update && sudo apt install locales
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8

locale  # verify settings

sudo apt install software-properties-common
sudo add-apt-repository universe

sudo apt update && sudo apt install curl -y
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg

echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null

# After running the above may need to hand-edit /etc/apt/sources.list.d/ros2.list
# and add bullseye after ubuntu and before main
# Because I was running rosdep install incorrectly before may need to run this:
sudo dpkg -i --force-overwrite <filename>
# and then the following to fix any broken packages
sudo apt-get install -f

sudo apt update && sudo apt install -y \
  python3-flake8-docstrings \
  python3-pip \
  python3-pytest-cov



 rosdep install --from-paths src --ignore-src -y --skip-keys "fastcdr rti-connext-dds-6.0.1 urdfdom_headers" --rosdistro humble --os=ubuntu:jammy

# Maybe toss a fix-broken in there somewhere
sudo apt --fix-broken install
```
