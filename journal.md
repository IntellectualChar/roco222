ROCO222
=======

## Lab journal
### 25th of September

#### First markdown document

Markdown - formating language
Used as it is easy to convert to HTML and other languages.

Using ** either side of a word mean when uploaded shows in bold. Other examples of formatting aer as such:

* This forms a bullet point
* Adding hashtags infront of a title determines how large the text is with one being the largest.
* Using (---) without brackets produces a solid line across the document as a way of breaking it up into sections.
* placing _ either side of a word formattes it as italics.
* =x7 under a word turns it into a header.
* and many more....

#### Command-line 101

![image-title-here](file:///home/student/Pictures/codeHELLO.png){:class="img-responsive"}

$ ls  
$ cd /tmp  
$ cd $HOME # what are those things starting with '$'?  
$ mkdir  
$ echo "Hello" > hello.md  
$ cat hello.md  
$ cp hello.md hello-again.md  
$ mv hello-again.md hello-hello.md  
$ rm hello.md  
$ rm -rf # be careful with that one!  
$ cat /proc/cpuinfo # is 'cpuinfo' a file??  

When we entered the code above startig with $, a message saying command not found was displayed. This is because $ is automatically placed infront of your code, so you do not have to enter it yourself. 

When removing the $ infront of the code it worked and found out the use off the following terms:

* echo - write arguments to outputs  
* cat - read files  
* rm - remove  
* mv - move  
* cp - copy   

#### Making a git repository

Started by going into the roco22 folder created by using cd roco222, then typing git init to create a repository in the files.
Then:
$ git config user.name "Firstname Surname"  
$ git config user.email "<email>"  

Then added the journal to the repositorry by typing git add journal.md, then a new commit using git commit.

The logs you make of adds to your git repository can be seen by typing git log.

#### Adding the journal to Github

Github is a remote internet server you can use to upload (push) and retrieve (pull) your commits (we are using it for the journal). It is partcualarly helpful for group projects as it allows multiple people to work on it from seperate loactions.

To do this you have to create an empty repository on your github account, then using the commands:

> git remote add origin https://github.com/<username>/<repositoryname>.git  
> git push -u origin master  

Then we logged into the github account through the terminal, and the journal was uploaded to my github.

To upload the file after changes again, we just had to type git add journal.md, git commit, then git push. Then using git pull you can retreive the file.

---

### Hacking into the robot


To hack into the robot enter the following commands:  
ping chapman   
ctrl c  
ssh nao@192.168.0.184 (ip)  
Enter password: nao  
Then you're in  

Type nano to edit a code to send  
type in the code  
mine:  
from naoqi import ALProxy  
tts = ALProxy("ALTextToSpeech", "localhost", 9559)  
tts.say("Hey now you're an all star, get your game on, go play!")  

then ctrl x  
yes  
enter the chosen name mine was: shrek.py  
then press enter  
  
To send to the robot type: python shrek.py  

---

### Building a motor

#### How does a motor work

A motor is built around the idea of electromagnatism. When an electric current passes through a coil in a magnetic field the magnetic force produces a tourque which turns the motor. The motor turns in the direction of the North pole. There are brushed motors and brushless motors, with different benefits to each design.

Brushed:

Esaily able to deliver current to the centeral coil, but is only intermitatly supplied.

Brushless:

The benefits of this are that there is no friction from the brushes so it is able to turn freely.

#### Simple design

We built a brushed DC electrical motor. It was made out of a cork with nails for axis with copper wire wrapped around to provide the current. We used paperclips for the axis hold and to hold the magnets in place.

Starting with a simple design, we chose 80 turns of the coil and used 12V and 2A supply.
Only able to use 2A due to the restrictions of the power supply.

We found while testing the roation of the motor was unreliable due to the motor only rotaing if started at the correct position.
Otherwise the forces from the coil and the magnets the oppose and cause the motor core to remain stationary. 
We also found when testing the comunter made of copper tape bend and was mishapped by the movement and pressuer from the brushes.

The simple motor is shown below:
(insert image here)

However this design was not very effective or reliable as it didnt continue to turn for very long. This was due to the holder for the axis not being tight and the holders for the magnets were easilyable to bend towards and away from the core of the motor. 

#### Improving the design

We added another coil with 80 turns at a right angle to the first coil. This will mean the motor will continue to move smoother and faster, also while allowing it to start in any orientation unlike the first motor.
Also Adding an extra section of cork onto the end with comuniter to help it keep its shape when moving. 
We tested the motor on a 12V source.

Updated motor:
(insert image here)

We found the coils to become warm quite quickly, so added insulation tape to the outside of the coils to help reduce this effect.  

(Updated image)

To reduce the vibrations of the motor we will reduce the diameter of the holders for the motor and secure the magnets in a more rigid hold.

### Incremental encoder

#### Building the circuit

The encoder consists of a LDR and a LED.

(image of circuit)

Our built circuit:
(image of circuit)

---

### Stepper motor

We were using a Unipolar Hybrid stepper motor with 6 connection wires. You can also get bipolar hybrid stepper motors. The difference between the different types are as follows:

#### Hybrid
(image of one)

This is the motor we used to test in the lab. They are controlled using the same method as a perminatnt magnet stepper motor. When the coil winding around the core is energized a north and south pole are created. The poles attract the perminat poles on the fine metal motor teeth. The motor moves one step at a time to align magnitized rotor teeth to the corrisponding windings. The two forms are bipolar and unipolar as described below. 

#### Bipolar
(image)

The bipolar motor has 4 wires, with no common center connection and it had two independent sets of coils. This means that the H-bridge channel on the arduino motor sheild can directly control each coil.

#### Unipolar
(image)

These have 5/6 wires, the one we used in the lab had 6 wires. It has 4 center coils with a common center connections. The common connection(s) need to be connected to ground and the other coil connections connected to the H-bridge chanel on the arduino motor sheild.

##### Full step mode

Only one phase is activated at one time. This mode gives a much lower torque than programming other modes.

(image of the code)

##### Double-step mode

This mode has the maximum torque rating, as two phases are always on.

(image of the code)

##### Half-step mode

Drive alternates between two phases on and a single phase on. This increases the angular resolution.

(image of the code)

##### Micro-step mode

This helps to make the movement of the stepper motor smoother. Winding current approximates a sinusoidal AC waveform.

(image of the code)

---

### Building a Robotic Arm

#### Using the 90 servos

The servos we used were SG90s. They are able to roate 90 degrees in both directions, making a total degree of freedom of 180.

#### Designing the arm

We designed the arm using Fusion 360.

#### First build and test

We first did a sinmple test the servos to check the wiring and mechanics of the arm by wiring in one of the servos at a time, by coding them to move in a constant 180 degree movement.

#### Improving the design

To improve the design we could add extra servos to allow for more degrees of freedom in the movement. Also could add a stepper motor as the base of the arm to allow it to rotate 360 degrees.

###ROS

#### Basic setup

Start off ros by opening a terminal and typing roscore to start roscore. 
 
By typing into another terminal rostopic list you are able to see the saved topics. To add to it you use rostopic pub the /..... std_msgs/String "....." Such as the message shown below:
* rostopic pub /test std_msgs/String "Hello"

You or someone else is then able to recall this message in another terminal by using the command rostopic echo /test. This will the print the saved message into their termnal. They can then write over the message for the other person to see. 

There are many other forms of data types other than std_msgs/String such as Byte, ByteMultiArray, Char, Float32, MultiArrayLayout and UInt16 etc..

#### RVIZ

First to install rviz type into a new terminal, sudo apt install rviz.

Once this is done you are then able to type rviz which will open the programme. However without anything running on ROS it was just an epty grid.

#### ROS on arduino

To start i downloaded rosserial using the phase shown below:
* sudo apt install ros-kinetic-rosserial-python ros-kinetic-rosserial-arduino

Also making it transparently avaliable in the arduino IDE using the two sections:
* cd $HOME/sketchbook/libraries
* rosrun rosserial_arduino make_libraries.py .

This means when i restarted arduion IDE I had access to the ROS examples. 

(image)
The above code allows 0-180 degrees of movement of the servo using ROS, except we used pin 3 to control our first servo.

Once uploaded we started rosserial in the terminal, 
*  rosrun rosserial_python serial_node.py /dev/ttyACM0
changing the serial port to match our board.

Then we used rostopic pub with parameters to move the arm.

#### 3D modelling the arm

The ROS node allows simple control of the servo motor but for more complex mtion planning we needed to describe its complete kinematic model. This inolves making a create ageometric and kinematic description of the arm using the URDF format. We do this in Rviz.

(image of code)
We uploaded the above code as the desciption of our robot arm by using the below commands:

* rosparam set robot_description -t models/robot-arm.urdf
* rosrun robot_state_publisher robot_state_publisher
* rosrun joint_state_publisher joint_state_publisher _use_gui:=true

Robot_state_publisher node reads the robots description and broadcasts the 6D transformations. While the joint_state_publisher node reads as well the robot description and creates a GUI with one slider per joint, making it easy to change the movement of the arm.

Then we added the robot model to RViz and set the Fixed frame to /base_link.

This then displays a model in RViz of a rough version of the robotic arm. 

The next step of development of ROS was to change the spesifications in the URDF file to match our robot arm design.

To then move the arm we editied the arduino code so it was able to read the joint state and control the motors.

