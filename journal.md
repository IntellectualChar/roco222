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

We were set to hack into nao and get it to say a phrase.

![Nao](https://github.com/IntellectualChar/roco222/blob/master/nao.jpg)

To hack into the robot enter the following commands:  
_ping chapman_  
_ctrl c_  
_ssh nao@192.168.0.184 (ip)_  
_Enter password: nao_  
Then you're in  

Type nano to edit a code to send  
Then type in the code you wish to use. 
mine was:  
_from naoqi import ALProxy_
_tts = ALProxy("ALTextToSpeech", "localhost", 9559)_ 
_tts.say("Hey now you're an all star, get your game on, go play!")- 

then ctrl x  
yes  
enter the chosen name mine was: shrek.py  
then press enter  
  
To send to the robot type:
_python shrek.py_  

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
![motor 1](https://github.com/IntellectualChar/roco222/blob/master/motor1.jpg)

However this design was not very effective or reliable as it didnt continue to turn for very long. This was due to the holder for the axis not being tight and the holders for the magnets were easilyable to bend towards and away from the core of the motor. Shown by us having to hold the brushes against the commutator:

[simple motor vid](https://www.youtube.com/watch?v=N0y_D7YMK28)

#### Improving the design

We kept the base as shown below:

![base](https://github.com/IntellectualChar/roco222/blob/master/motor_base.jpg)

We added another coil with 80 turns at a right angle to the first coil. This will mean the motor will continue to move smoother and faster, also while allowing it to start in any orientation unlike the first motor.
Also Adding an extra section of cork onto the end with comuniter to help it keep its shape when moving. 
We tested the motor on a 12V source.

We found the coils to become warm quite quickly, so added insulation tape to the outside of the coils to help reduce this effect.  

![Basic motor final](https://github.com/IntellectualChar/roco222/blob/master/Motor_improved.jpg)

To reduce the vibrations of the motor we will reduce the diameter of the holders for the motor and secure the magnets in a more rigid hold.

To make the design more rigid I decided to make the motor out of lego, as this will give more even axis and strong non flexible holders for the magnets. First trialed one design as shown below:

![lego motor core](https://github.com/IntellectualChar/roco222/blob/master/Motor_trial.jpg)

However we found that the base strucure and stand for the motor was not stable enough to with stand its movement, so adding more lego bricks and a stable base lead to the final design as shown below:

![Final motor](https://github.com/IntellectualChar/roco222/blob/master/Final_motor.jpg)

The below video shows a slow version of our motors movement:

[motor move](https://www.youtube.com/watch?v=8WvBiNtY8GU)

### Incremental encoder

#### Building the circuit

The encoder consists of a LDR and a IR LED.

![encoder](https://github.com/IntellectualChar/roco222/blob/master/Encoder_circuit.jpg)

Our built circuit:
![encoder2](https://github.com/IntellectualChar/roco222/blob/master/Encoder.jpg)

---

### Stepper motor

We were using a Unipolar Hybrid stepper motor with 6 connection wires. You can also get bipolar hybrid stepper motors. The difference between the different types are as follows:

#### Hybrid

![hybrid](https://github.com/IntellectualChar/roco222/blob/master/Hybrid_motor.jpg)

This is the motor we used to test in the lab. They are controlled using the same method as a perminatnt magnet stepper motor. When the coil winding around the core is energized a north and south pole are created. The poles attract the perminat poles on the fine metal motor teeth. The motor moves one step at a time to align magnitized rotor teeth to the corrisponding windings. The two forms are bipolar and unipolar as described below. 

#### Bipolar

![bipolar](https://github.com/IntellectualChar/roco222/blob/master/Bipolar.jpg)

The bipolar motor has 4 wires, with no common center connection and it had two independent sets of coils. This means that the H-bridge channel on the arduino motor sheild can directly control each coil.

#### Unipolar

![uni](https://github.com/IntellectualChar/roco222/blob/master/Unipolar.jpg)

These have 5/6 wires, the one we used in the lab had 6 wires. It has 4 center coils with a common center connections. The common connection(s) need to be connected to ground and the other coil connections connected to the H-bridge chanel on the arduino motor sheild.

#### Our set up

![stepper motor](https://github.com/IntellectualChar/roco222/blob/master/Steppermotor.jpg)

The setup for the code is as follows:

_#define DIR_A 12_
_#define DIR_B 13_

_#define SPEED_A 3
#define SPEED_B 11_

_#define PERIOD 3_


_void setup() {
//Setup Channel A
pinMode(12, OUTPUT); //Initiates Motor Channel A pin
pinMode(9, OUTPUT); //Initiates Brake Channel A pin
}_

_void setup2() {
//Setup channel B
pinMode(13, OUTPUT);
pinMode(8, OUTPUT); 
digitalWrite(9, LOW); //Disengage the Brake for Channel A
digitalWrite(8,  LOW); //Disengage the Brake for Channel B
}_


##### Full step mode

![full](https://github.com/IntellectualChar/roco222/blob/master/Fullstep_diagram.jpg)

Only one phase is activated at one time. This mode gives a much lower torque than programming other modes.

![fullstep](https://github.com/IntellectualChar/roco222/blob/master/Fullstep.jpg)

##### Double-step mode

![double](https://github.com/IntellectualChar/roco222/blob/master/Fullstep2_diagram.jpg)

This mode has the maximum torque rating, as two phases are always on.

![doublestep](https://github.com/IntellectualChar/roco222/blob/master/Fullstep2.jpg)

##### Half-step mode

![half](https://github.com/IntellectualChar/roco222/blob/master/Halfstep_table.jpg)

Drive alternates between two phases on and a single phase on. This increases the angular resolution.

![Halfstep1](https://github.com/IntellectualChar/roco222/blob/master/Half_step1.jpg)
![Halfstep2](https://github.com/IntellectualChar/roco222/blob/master/Half_step2.jpg)

##### Micro-step mode

![micro](https://github.com/IntellectualChar/roco222/blob/master/Microstepping.jpg)

This helps to make the movement of the stepper motor smoother. Winding current approximates a sinusoidal AC waveform.



---

### Building a Robotic Arm

#### Using the 90 servos

The servos we used were SG90s. They are able to roate 90 degrees in both directions, making a total degree of freedom of 180.
The wiring of the servo is shown below:

![servo](https://github.com/IntellectualChar/roco222/blob/master/Servo.jpg)

#### Designing the arm

We designed the arm using Fusion 360.

![fusion](https://github.com/IntellectualChar/roco222/blob/master/arm_fusion.png)

#### First build and test

![side](https://github.com/IntellectualChar/roco222/blob/master/arm_side.jpg)

![top](https://github.com/IntellectualChar/roco222/blob/master/arm_top.jpg)

We first did a sinmple test the servos to check the wiring and mechanics of the arm by wiring in one of the servos at a time, by coding them to move in a constant 180 degree movement.

![servo movement](https://github.com/IntellectualChar/roco222/blob/master/servo_control.jpg)

Video to show our arm in motion:
[arm movement](https://www.youtube.com/watch?v=cOelTML7cZo)

#### Improving the design

To improve the design we could add extra servos to allow for more degrees of freedom in the movement. Also could add a stepper motor as the base of the arm to allow it to rotate 360 degrees.

###ROS

#### Basic setup

Start off ros by opening a terminal and typing roscore to start roscore. 
 
By typing into another terminal rostopic list you are able to see the saved topics. 

![rostopic](https://github.com/IntellectualChar/roco222/blob/master/Rostopic.jpg)

To add to it you use rostopic pub the /..... std_msgs/String "....." Such as the message shown below:
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

![ROS servo](https://github.com/IntellectualChar/roco222/blob/master/ROS_servo.jpg)

The above code allows 0-180 degrees of movement of the servo using ROS, except we used pin 3 to control our first servo.

Once uploaded we started rosserial in the terminal, 
*  rosrun rosserial_python serial_node.py /dev/ttyACM0
changing the serial port to match our board.

Then we used rostopic pub with parameters to move the arm.

#### 3D modelling the arm

The ROS node allows simple control of the servo motor but for more complex mtion planning we needed to describe its complete kinematic model. This inolves making a create ageometric and kinematic description of the arm using the URDF format. We do this in Rviz.

![URDF](https://github.com/IntellectualChar/roco222/blob/master/URDF1.jpg)

We uploaded the above code as the desciption of our robot arm by using the below commands:

* rosparam set robot_description -t models/robot-arm.urdf
* rosrun robot_state_publisher robot_state_publisher
* rosrun joint_state_publisher joint_state_publisher _use_gui:=true

Robot_state_publisher node reads the robots description and broadcasts the 6D transformations. While the joint_state_publisher node reads as well the robot description and creates a GUI with one slider per joint, making it easy to change the movement of the arm.

Then we added the robot model to RViz and set the Fixed frame to /base_link.

This then displays a model in RViz of a rough version of the robotic arm. 

The next step of development of ROS was to change the spesifications in the URDF file to match our robot arm design.

To then move the arm we editied the arduino code so it was able to read the joint state and control the motors.

