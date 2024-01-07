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
