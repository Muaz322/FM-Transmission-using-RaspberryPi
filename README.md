# FM-Transmission-using-RaspberryPi
Hacking FM frequency of a station 


FM transmitter Using Raspberry Pi
Description:

•	In this project we will be using raspberry pi 3 to to transmit FM signals. The OS we will be using is Kali Linux and 		a code of C. 

•	What it will do is it will transmit a .wav (audio file of our choice) on a frequency of our choice I will do it on 100 MHz.

Software:

•	Raspberry pie 3 OS Kali Linux

•	Terminal

Components Required:
•	Wi-Fi antenna dongle

•	Raspberry Pi 3
 

•	VGA OR HDMI cable for output to LCD monitor

•	LCD Monitor

•	Keyboard 

•	Mouse

•	SD Card at least 16GB

•	Earphone for mobile to play FM




Procedure:
1.	Setup your raspberry Pi connect the VGA/HDMI cable into your LCD monitor and power it up. 

•	If you see this image it means you have kali linux installed



•	If screen remain blank it means you don’t have any OS on SD Card or your board is not working correctly

2.	After your OS boots up your startup screen would look like this open up the terminal.
 


3.	If you are using Raspbian OS first you need to install sndfile library by entering the command 

		sudo apt-get install libsndfile1-dev.

4.	If you are using Kali linux it should have rpi-mailbox the August 2015 release already have this library built in.

5.	Now first make a directory by the name PI_FM and change your directory to it
		
		mkdir PI_FM
   		 cd PI_FM


6.	Now we clone the files from the github using the following code

		sudo git clone https://github.com/markondej/fm_transmitter

7.	The downloaded files are C code so you need a compiler type this

		sudo apt-get install gcc g++ make

8.	Now change your directory to fm_transmitter and compile code using 

		cd fm_transmitter
		sudo make


9.	Now the final part is to run the code. In code after –f is the frequency and after –r is the wav file name

		sudo ./fm_transmitter -f 100  -r acoustic_guitar_duet.wav

10.	Now plug in your FM and tune in 100Mhz and you will be able to listen to this file.

11.	If you get an error by playing your own .wav file saying ‘corrupted data’ try using the following command

		sudo apt-get install sox libsox-fmt-mp3
		sox my-audio.mp3 -r 22050 -c 1 -b 16 -t wav my-converted-audio.wav
		sudo ./fm_transmitter -f 100.6 my-converted-audio.wav 
 



For Complete description open pdf


