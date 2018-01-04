# Use Voice Search to make a Video Playlist

## Introduction to 

## Installing the Libraries

### Nginx
This is a light-weight webserver that runs on the raspberry PI. We will use it to serve the player.html that we will create 

### Install Python 3 and PIP

### Speech Recognition

Quickstart: pip install SpeechRecognition. See the “Installing” section for more details.

To quickly try it out, run python -m speech_recognition after installing.

#### Python
The first software requirement is **Python 2.6, 2.7, or Python 3.3+**. This is required to use the library.

#### PyAudio (for microphone users)
PyAudio is required if and only if you want to use microphone input (**Microphone**). PyAudio version 0.2.11+ is required, as earlier versions have known memory management bugs when recording from microphones in certain situations.

If not installed, everything in the library will still work, except attempting to instantiate a Microphone object will raise an AttributeError.

On Debian-derived Linux distributions (like Ubuntu and Mint), install PyAudio using APT:<br/>
- sudo apt-get install python-pyaudio python3-pyaudio <br/>

If the version in the repositories is too old, install the latest release using Pip:<br/>
- sudo apt-get install portaudio19-dev python-all-dev python3-all-dev
- sudo pip install pyaudio (replace pip with pip3 if using Python 3).

**FOR MORE INFO: http://people.csail.mit.edu/hubert/pyaudio/#downloads** <br/>
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;&nbsp;&nbsp; **https://pypi.python.org/pypi/SpeechRecognition/**

### Google API
You can either use a package manager or download and install the Python client library manually:

#### Managed installation
Use pip or setuptools to manage your installation:

- **pip (preferred)**:
sudo pip install --upgrade google-api-python-client
      
- **Setuptools**: 
sudo easy_install --upgrade google-api-python-client

**FOR MORE INFO: https://developers.google.com/api-client-library/python/start/installation** <br/>
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;&nbsp;&nbsp; **https://developers.google.com/api-client-library/python/**

### Selenium
This library enables us to open a web browser from python and simulate button clicks on hosted html pages.  

#### Installation
To install the selenium module, type the command:<br/>

- pip install -U selenium
Then get the web driver from http://docs.seleniumhq.org/projects/webdriver. There are all kind of webdrivers including:

ChromeDriver
FirefoxDriver
RemoteWebDriver
 
### Aslaaudio
This library enables us to control speaker volume through python. <br/>
- sudo -H pip3 install pyalsaaudio

### Firefox browser Raspberry PI

**Install dirmngr:**	<br/>	
- sudo apt install dirmngr <br/>

**Add the repository to your sources:** <br/>
- echo "deb http://ppa.launchpad.net/ubuntu-mozilla-security/ppa/ubuntu trusty main" | sudo tee /etc/apt/sources.list.d/firefox.list <br/>
- echo "deb-src http://ppa.launchpad.net/ubuntu-mozilla-security/ppa/ubuntu trusty main" | sudo tee /etc/apt/sources.list.d/firefox-source.list <br/>

**Install Firefox: ** <br/>
- sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys A6DCF7707EBC211F <br/>
- sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 9BDB3D89CE49EC21 <br/>
- sudo apt update && sudo apt install firefox <br/>

### Setting up the GPIO pins on a Raspberry PI

