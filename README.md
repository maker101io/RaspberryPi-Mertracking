# RaspberryPi-Mertracking
Raspberry Pi + OpenCV + Tracking + Trigger Project </br>
Full tutorial for motion tracking: https://bit.ly/MertArduino

# Install Guide
1) Make sure pip is installed </br>
https://www.pyimagesearch.com/2018/09/19/pip-install-opencv/

&emsp; <code> sudo apt-get install python pip </code> </br>

2) Install OpenCV 3. Follow all steps for python 3 instructions </br>
https://www.pyimagesearch.com/2016/04/18/install-guide-raspberry-pi-3-raspbian-jessie-opencv-3/

3) Setup I2C on your Raspberry Pi </br>
https://learn.adafruit.com/adafruits-raspberry-pi-lesson-4-gpio-setup/configuring-i2c

4) Install the Adafruit stepper motor HAT library </br>

&emsp; <code> sudo pip install git+https://github.com/adafruit/Adafruit-Motor-HAT-Python-Library </code> </br>

5) If you are using a Raspberry Pi Stepper Motor Expansion Board other than the Adafruit Stepper Motor HAT (just like in the video), then update the I2C address or frequency value with the following. (This address is only compatible with the board in the video, default value is blank for Adafruit Stepper Motor HAT) </br>

&emsp; <code> self.mh = Adafruit_MotorHAT() </code> &nbsp; to &nbsp; <code> self.mh = Adafruit_MotorHAT(0x6F) </code> &nbsp; in the source code (mertracking.py) </br>

&emsp; for mor details: http://www.raspberrypiwiki.com/index.php/Robot_Expansion_Board

6) Make sure to create your virtual environment with the extra flag </br>

&emsp; <code> mkvirtualenv cv --system-site-packages -p python3 </code>

7) Source your bash profile </br>

&emsp; <code> source ~/.profile </code>

8) Open Terminal and Activate your virtual environment </br>

&emsp; <code> workon cv </code>

9) Clone this repository </br>

&emsp; <code> git clone git@github.com:MertArduino/RaspberryPi-Mertracking.git </code>

10) Navigate to the directory </br>

&emsp; <code> cd RaspberryPi-Mertracking </code>

11) Install dependencies to your virtual environment </br>

&emsp; <code> pip install imutils RPi.GPIO </code>

12) Run the Code </br>

&emsp; <code> python mertracking.py </code>

# Setting Parameters
mertracking.py has a couple parameters that you can set </br>

&emsp; <code> MOTOR_X_REVERSED = False </code> </br>
&emsp; <code> MOTOR_Y_REVERSED = False </code> </br>
&emsp; <code> MAX_STEPS_X = 20 </code> </br>
&emsp; <code> MAX_STEPS_Y = 10 </code> </br>
&emsp; <code> RELAY_PIN = 22 </code> </br>
&emsp; <code> self.mh = Adafruit_MotorHAT(0x6f) </code> &nbsp; I2C Address or Frequency </br>
&emsp; <code> self.sm_x.setSpeed(5) </code> &nbsp; Speed of the Stepper Motor 1</br>
&emsp; <code> self.sm_y.setSpeed(5) </code> &nbsp; Speed of the Stepper Motor 2</br>
&emsp; <code> self.sm_x = self.mh.getStepper(200, 1) </code> &nbsp; Steps/Rev of the Stepper Motor 1</br>
&emsp; <code> self.sm_y = self.mh.getStepper(200, 1) </code> &nbsp; Steps/Rev of the Stepper Motor 2</br>
&emsp; <code> time.sleep(1) </code> &nbsp; Delay Time for the Relay Trigger </br>

&emsp; <code> Adafruit_MotorHAT.MICROSTEP </code> &nbsp; You can change the step type with the following commands </br>

&emsp; <code> MICROSTEP </code> </br>
&emsp; <code> SINGLE </code> </br>
&emsp; <code> DOUBLE </code> </br>
&emsp; <code> INTERLEAVE </code> </br>
