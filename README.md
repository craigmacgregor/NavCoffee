# NavCoffee
Software for the NavCoffee Twitch livestream, running on a Raspberry Pi
The livestream can be found at twitch.tv/navcoffee

This project was created by the NavCoin Core summer interns of 2018/19 to engage with the community
This repo has been created to allow community members to recreate the livestream themselves

To recreate this project you will need:
 - A raspberry pi (Raspberry Pi 3 Model B was used) with Raspbian
 - A usb webcam
 - A breadboard and components to create a controller (If not wanting to controll through software)
 - A Twitch account
 - A NavCoin wallet

To run your own crypto-coffee livestream (or similar), follow the instructions below:
 - Clone this repo into the /home/pi/Documents/ directory of your Pi
 - Open query_wallet.py in your text editor/IDE of choice
	- On line 12 enter the address you wish to receive NavCoin donations at
 - Type "crontab -e" into your terminal
 - Add the line "*/2 * * * * python3 ~/Documents/query_wallet.py" to ensure the stream will update donation information every 2 minutes
 - Open stream.sh in your text editor of choice
	- On line 10 enter your stream key for twitch, be sure not to show this on stream or to anyone you don't trust
 - Replace nav_qr.png with a picture of a payment request to your address, name it nav_qr.png also
 - Wire up a breadboard with buttons and LEDs if you plan to use hardware to control your stream (example picture given as breadboard_example.jpg)
	- I recommend following the guide here: https://projects.raspberrypi.org/en/projects/gpio-music-box/6
	  if you are not familiar with the pi and electronics
 - Be sure to wire the start button to GPIO pin 17, stop to 27 and redeem coffee to 22, the start LED to 6 and coffee available LED to 13
 - You may need to install Selenium and add chromedriver to your path
 - To activate the stream run "sudo python3 controller.py" in the Documents directory and press your physical start button
 - Alternatively, run "./stream.sh" and "./stop_stream.sh" to controll via the terminal (controller.py is not necessary for software control)

In the event of a power cut, simply rerun "sudo python3 controller.py" to activate your control board



