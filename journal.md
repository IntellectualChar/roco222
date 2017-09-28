#ROCO222

## 1st lab
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

echo - write arguments to outputs  
cat - read files  
rm - remove  
mv - move  
cp - copy   

#### Making a git repository

Started by typing git init to create a repository in the files.
Then:
$ git config user.name "Firstname Surname"  
$ git config user.email "<email>"  

Then added the journal to the repositorry by typing git add journal.md, then a new commit using git commit.

The logs you make of adds to your git repository can be seen by typing git log.

#### Adding the journal to Github

Github is a remote internet server you can use to upload (push) and retrieve (pull) your commits (we are using it for the journal). It is partcualarly helpful for group projects as it allows multiple people to work on it from seperate loactions.

To do this you have to create an empty repository on your github account, then using the commands:

> git remote add origin https://github.com/username/repositoryname.git
> git push -u origin master

Then we logged into the github account through the terminal, and the journal was uploaded to my github.

To upload the file after changes again, we just had to type git push. Then using git pull you can retreive the file.





