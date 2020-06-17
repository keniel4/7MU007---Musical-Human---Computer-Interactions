==RYTHEM FINDER==

The idea behind this project is to create a children’s musical learning-based game for ages 4-8. Its main focus being around timing, the player has to play along to the sequence in time in order to progress onto the next level. Each level advances in complexity, thus engaging with the players listening skills, timing, and the ability to maintain a rhythmic pattern. There are two components in which the user interacts with the game, this being the hardware and software. This document will detail all the required pieces of hardware and instruction to this specific build. It will also encompass a breakdown of the software to allow for users to recreate. 


PLEASE NOTE: You will need to download the three ZIP folders, wich will contain all the asociated images that correspond with the relevant section. The text will refere to these images throughout.





==WHAT YOUT WILL NEED:==

1 x Arduino Board

1 x Solderless Breadboard

1 x USB 2.0 Type A/B Cable

8 x Jumper Cables

3 x Momentary Push Buttons (Yellow, Black, Green)

3 x 1Mom






==HOW TO BUILD YOUR OWN== (Configuring the hardware)


Step 1:

Download and install, then open Arduino IDE on your computer. (Software can be found at: https://www.arduino.cc/en/Main/Software)

Step 2:

Connect Arduino board to the computer using the USB cable (Type A/B).

Step 3:

Configure Arduino by uploading Serial_Print.ino to the board. Once Arduino IDE is installed, select the icon with the up pointing arrow to open the file from where it has been downloaded. After the file has been opened, select the tick icon to verify the code and then select the right pointing arrow icon to upload it to the Arduino. Once this has been done the code will remain on the Arduino board until indefinitely.

Step 4: 

Connect the Momentary push buttons to the Breadboard and the 1mom resistors in the sequence as displayed below.

Step 5:

Connect the ground (GND) from the Arduino to the negative (black) strip on the breadboard using solderless male to male jumper cables. Connect the power (5V) from the Arduino to the positive (red) strip on the breadboard. 

Step 6:

Insert a jumper cable next to the jumper cable carrying the 5V from the Arduino to the breadboard. Insert the other end of the jumper cable next to the Momentary button as displayed. In pictures.

Step 7:

Connect a jumper cable next to the momentary button as displayed in picture, this signal will then be connected to the first analogue input of the Arduino (A0). Repeat this  for the other two buttons.


Step 8:
The final setup should look like the image displayed with all the momentary buttons supplied with 5V and a analogue output connected to the Arduino





==PURE DATA PATCH COMPONENTS==

Graphic user Interface:
The main graphic user interface is designed with the particular user in mind which is ages 4-7. Its visually pleasing for this purpose and must conveys as much information visually. The colours of the buttons correlate with the physical buttons. The user can see what’s being played by themselves and the computer. As the game is focused around timing and mimicking the drum sequences, this is important for the user to interpret on a visual level and an audio. The yellow box represents the Kick, the black box represents the snare and the green representing the hihat.


St/Stp - Level Select:
From the section of the patch the user can select the midi file with the level of complexity ranging from 1 to 3. The user can also start and stop the sequence. The  midi file is loaded and read 


Sequence Trigger Visual:
The midi notes within the midi file are then received remotely, are then shown as bangs each box representing either the kick snare and hi-hat. 


Sample Playback:
The audio samples are triggered when they receive a bang from their corresponding colour. This allows the user to hear the sequence and see it in the flashing of the bangs. the timing information is then compared with the timing information of the user and the difference is used to then give the user a visual feedback via the Accuracy bar.



Arduino input:


Manual Trigger Visual:
The users physical input from the buttons pressed, trigger the corresponding bangs and it can be seen by the user so the timing is based around the user seeing that the buttons are pressed in time, so there is no audio triggered when the user presses a button it is only convey visual feedback. The timing information of the user is compared to the computer. 



Lose:
When the users timing falls out of time by 500ms it will trigger the metronome to count down for 20 secs and then display a x in the loose box if the user maintains timing for 20 secs then an x is displayed in the win box
