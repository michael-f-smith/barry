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

sudo apt update && sudo apt install -y \
  python3-flake8-docstrings \
  python3-pip \
  python3-pytest-cov \
  ros-dev-tools
```
