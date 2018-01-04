# Use Voice Search to make a Video Playlist

## Introduction to Today's Workshop
![alt text](https://raw.githubusercontent.com/username/projectname/branch/path/to/img.png)

## Installing the Libraries
To enable the functionalities of all the different functions we will be using on python. Certain libraries need to be installed to enable us to use these "functionalities" for the further use.

### Nginx
This is a light-weight webserver that runs on the raspberry PI. We will use it to serve the player.html that we will create <br\>
We’ll update our packages and then install nginx. Open up the terminal and run these commands, one after the other:

- sudo apt-get update
- sudo apt-get install nginx <br/>

Say yes when prompted. Nginx is the server itself, and it’s very efficient.<br/>

Access your website by typing your public IP address into your web browser’s address bar from any internet-connected device. Your site will just have the nginx welcome page for now,  located at /var/www/html. You can remove that and create a file calledindex.html, if you  and continue from there. <br/>
**In our case, move all the content from RPIvideoplayer to /var/www/html on your Raspberry PI**

### Install Python 3 and PIP
Usually Python3 is pre-installed when you install Raspbian on your RAspberry PI. <br\>

But, not all Python packages are available in the Raspbian archives, and those that are can sometimes be out-of-date. If you can't find a suitable version in the Raspbian archives, you can install packages from the Python Package Index (PyPI). To do so, use the pip tool.

**Pip** is installed by default in Raspbian Jessie (but not Raspbian Wheezy or Jessie Lite). You can install it with apt:

-sudo apt-get install python3-pip

### Speech Recognition
Library for performing speech recognition, with support for several engines and APIs, online and offline.

#### Installation: 
- pip install SpeechRecognition *(Installs Google Speech recognition API)*
- sudo python -m speech_recognition *(to test it)* 

#### Python
The first software requirement is **Python 2.6, 2.7, or Python 3.3+**. This is required to use the library.

#### PyAudio *(for microphone users)*
PyAudio is required if and only if you want to use microphone input (**Microphone**). PyAudio version 0.2.11+ is required, as earlier versions have known memory management bugs when recording from microphones in certain situations.

If not installed, everything in the library will still work, except attempting to instantiate a Microphone object will raise an AttributeError.

On Debian-derived Linux distributions *(like Ubuntu and Mint)*, install PyAudio using APT:<br/>
- sudo apt-get install python-pyaudio python3-pyaudio <br/>

If the version in the repositories is too old, install the latest release using Pip:<br/>
- sudo apt-get install portaudio19-dev python-all-dev python3-all-dev
- sudo pip install pyaudio *(replace pip with pip3 if using Python 3)*.

**FOR MORE INFO: http://people.csail.mit.edu/hubert/pyaudio/#downloads** <br/>
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;&nbsp;&nbsp; **https://pypi.python.org/pypi/SpeechRecognition/**

### Google API
In our application we are using a library called - **gTTS (text to speech library)** <br\>
gTTS is a module and command line utility to save spoken text to mp3.
It uses the Google Text to Speech (TTS) API.
This module supports many languages and sounds very natural.

#### Installation
Install with the python package tool (pip):
- sudo pip install gTTS <br\>

#### Example
```python
from gtts import gTTS
import os
tts = gTTS(text='Good morning', lang='en')
tts.save("good.mp3")
os.system("mpg321 good.mp3")
```
If you want to test it on the command line use:
- gtts-cli.py “Hello” -l ‘en’ -o hello.mp3 <br\>

In addition, we are also using an inbuilt library, that come with speechrecognition library, when you install it. 
**FOR MORE INFO: https://pythonprogramminglanguage.com/text-to-speech/

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
The newest version of Raspbian has the RPi.GPIO library pre-installed. You’ll probably need to update your library, so using the command line, run:
- sudo apt-get install rpi.gpio
If it isn’t already installed it will be installed. If it is already installed it will be upgraded if a newer version is available.

#### Using the RPi.GPIO Library
Now that you’ve got the package installed and updated, let’s take a look at some of the functions that come with it. Open the Leafpad text editor and save your sketch as “myInputSketch.py”. From this point forward, we’ll execute this script using the command line:

-sudo python myInputSketch.py

All of the following code can be added to this same file. Remember to save before you run the above command. To exit the sketch and make changes, press Ctrl+C.

To add the GPIO library to a Python sketch, you must first import it:
```python
import RPi.GPIO as GPIO
```

Then we need to declare the type of numbering system we’re going to use for our pins:
```python
#set up GPIO using BCM numbering
GPIO.setmode(GPIO.BCM)
#setup GPIO using Board numbering
GPIO.setmode(GPIO.BOARD)
```
#### Examples: 
https://thepihut.com/blogs/raspberry-pi-tutorials/27968772-turning-on-an-led-with-your-raspberry-pis-gpio-pins
https://www.raspberrypi-spy.co.uk/2012/05/install-rpi-gpio-python-library/
