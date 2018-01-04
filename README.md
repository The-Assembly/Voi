# Use Voice Search to make a Video Playlist

## Introduction to 

## Installing the Libraries

### Nginx
This is a light-weight webserver that runs on the raspberry PI. We will use it to serve the player.html that we will create 

### Install Python 3 and PIP

### Speech Recognition

### Google API

### Selenium
This library enables us to open a web browser from python and simulate button clicks on hosted html pages.  
 
### Aslaaudio
This library enables us to control speaker volume through python. <br/>
- sudo -H pip3 install pyalsaaudio

### Firefox browser Raspberry PI

1. Install dirmngr:	<br/>	
- sudo apt install dirmngr <br/>

2. Add the repository to your sources: <br/>
- echo "deb http://ppa.launchpad.net/ubuntu-mozilla-security/ppa/ubuntu trusty main" | sudo tee /etc/apt/sources.list.d/firefox.list <br/>
- echo "deb-src http://ppa.launchpad.net/ubuntu-mozilla-security/ppa/ubuntu trusty main" | sudo tee /etc/apt/sources.list.d/firefox-source.list <br/>

3. Install Firefox <br/>
- sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys A6DCF7707EBC211F <br/>
- sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 9BDB3D89CE49EC21 <br/>
- sudo apt update && sudo apt install firefox <br/>

### Setting up the GPIO pins on a Raspberry PI

