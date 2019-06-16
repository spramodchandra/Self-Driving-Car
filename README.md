# Autonomous Racing car With a Raspberry Pi and a Pi Camera.
For a <a href="https://sites.google.com/usc.edu/raceon/home?authuser=0">racing competition</a> at USC couple of my friends and I built and programmed an autonomous car using raspberry pi and a pi camera. We used OpenCV for image processing and pid cotroller for controlling the car. We secured 2nd position in this competition.
<br>
We implemented a multithreaded program to distribute the load equally and we were able to do 40fps.
### Hardware
<ul>
  <li> Car Chassis – <a href="https://www.integy.com/st_prod.html?p_prodid=30486&p_catid=370">3Racing Sakura XI Sport 1/10 RC Touring Car Ver.NU<a/> </li>
  <li> Motor - <a href="https://hobbyking.com/en_us/540-6527-brushed-motor-90w.html"> MABUCHI 540-6527 Brushed Motor 90W</a></li>
  <li> Servo – <a href="https://hobbyking.com/en_us/towerpro-mg946r-12kg-0-20sec-55g.html">TowerPro MG946R Servo 25T 13kg / 0.11sec / 55g</a></li>
  <li> Battery – <a href="https://hobbyking.com/en_us/zippy-4000mah-2s1p-25c-car-lipoly-roar-approved-de-warehouse.html">Motor – ZIPPY 4000mAh 2S1P 25C Car Lipoly</a></li>
  <li> Electronic Speed Controller – <a href="https://hobbyking.com/en_us/turnigy-20a-brushed-esc.html">Turnigy 20A BRUSHED ESC</a></li>
  <li> Power Supply – <a href="https://hobbyking.com/en_us/turnigy-5a-8-26v-sbec-for-lipo.html">Turnigy 5A (8-26v) SBEC for Lipo</a></li>
  <li> Raspberry Pi – <a href="https://www.newark.com/raspberry-pi/rpi3-modbp/sbc-arm-cortex-a53-1gb-sdram/dp/49AC7637">RPI3-MODBP</a></li>
  <li> Pi Camera – <a href="https://www.newark.com/raspberry-pi/rpi-8mp-camera-board/camera-board-8-mp-raspberry-pi/dp/77Y6521">RPI 8MP CAMERA BOARD</a></li>
  <li> Pi HAT – <a href="https://www.adafruit.com/product/2310">Adafruit Perma-Proto HAT for Pi Mini Kit - No EEPROM</a></li>
  <li> Battery Charge – <a href="https://hobbyking.com/en_us/imax-b6-ac-dc-charger-5a-50w-with-us-plug-copy.html">IMAX B6 AC-DC Charger 5A 50W With US Plug</a></li>
 </ul>
 
 ### Software
 <ul>
  <li> Python + Numpy + OpenCV on the Raspberry Pi</li>
 </ul>
 
 ### Image Processing
 To control the car and to navigate it along the track, we need to predict the turns, so as to dynamically change the speed.
 First we define a region of interest.
 Next convert the image into b/w.( This step is required for using <a href="https://docs.opencv.org/3.3.1/d4/d73/tutorial_py_contours_begin.html">contours</a>).
 Based on the contours, we select the one with maximum region. Based on the boundary points, we divide the image into 5 parts, and find the mid points. Using these mid points we can determine the curvature of the track.

Below images show the image and processed image.
<br/>
<img src="https://raw.githubusercontent.com/spramodchandra/Self-Driving-Car/master/images/original.jpg"/>
<img src="https://raw.githubusercontent.com/spramodchandra/Self-Driving-Car/master/images/processedimage.jpg"/>
