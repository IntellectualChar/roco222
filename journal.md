#ROCO222

## Lab journal
### 25th of September

#### First markdown document

Markdown - formating language
Used as it is easy to convert to HTML and other languages.

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

>echo - write arguments to outputs  
>cat - read files  
rm - remove  
>mv - move  
cp - copy   

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

### Building a motor

#### Simple design

We built a brushed DC electrical motor  

Starting with a simple design, we chose 80 turns of the coil and used 12V and 2A supply.
Only able to use 2A due to the restrictions of the power supply.

We found while testing the roation of the motor was unreliable due to the motor only rotaing if started at the correct position.
Otherwise the forces from the coil and the magnets the oppose and cause the motor core to remain stationary. 
We also found when testing the comunter made of copper tape bend and was mishapped by the movement and pressuer from the brushes.

The simple motor is shown below:
(insert image here)

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

(image of circuit)

Our built circuit:
(image of circuit)

### Stepper motor

### Building a Robotic Arm

#### Using the 90 servos

#### Designing the arm

#### First build and test

#### Improving the design
