# The Point
The point of this script is to use the github feature of unlimited repositories, as a way to share large amount of data without having to upload it on GoogleDrive/DropBox(As those have limits on amount of data).

After an Upload the script asks the user for where does he want to put the ".map file", note that information stored in this file is later used to Download the data back from github.(So anyone with this script and the .map file can download the data uploaded by themselves.)

The idea is that if you have large amounts of data that needs to be shared then you can upload it to github via this script and share a relatively tiny .map file(generally under a MB) to the people you want to share this script to.





# Installation(For Linux and MacOS)
->Install Python(And make sure that version is greater than 3.6.(To check do "python3 --version"))

->Install pygithub module
    
    pip install pygithub

make sure you have git installed to check do->
    
    git --version

if the above command throws an error install git.

Now clone this repo

    git clone https://github.com/Shwalia/uploadit.git


# Installation (For Windows)
-> Install Ubuntu on WSL2(https://ubuntu.com/tutorials/install-ubuntu-on-wsl2-on-windows-10#1-overview)

Switch to WSL2

-> Install git 
    
    sudo apt install git

-> Install pygithub

    pip install pygithub

Now clone this repo

    git clone https://github.com/Shwalia/uploadit.git


# Things To Keep In Mind

->Directory to be uploaded must not any spaces in its name ("My_Photos" is allowed and not "My Photos").However files/directories within that may have spaces in their name(ex-> "My_photos/national park trip/" is allowed).

->While Downloading make sure you have twice the amount of free storage in your partition as the size of the folder to be downloaded.(If the folder to be downloaded is 10GB then make sure that your disk has atleast 20GB of free space.)

->While Uploading make sure partition containing raw_path has as much free storage available as the size of the folder to be uploaded.(If the folder to uploaded is 10GB then make sure that you have an extra 10GB of free disk space available)

->You may only upload a folder and not a file, If you want to upload a file move that file in an empty folder and upload that folder.



# Usage(Windows)
Before we proceed make sure that you have completed the Installation of prerequisites.

All the commands shown are to be executed in WSL2.

You first need to understand the linux file system and how to navigate it.https://www.redhat.com/sysadmin/navigating-linux-filesystem

Also first we need to know where our partitions are mounted in WSL2.

All our drives are mounted in **/mnt**. for ex-> our 'D' drive is mounted at /mnt/d. So we will find all our files in the 'D' drive in **/mnt/d**. 

We can use this information to upload any file from our drives.(for example if we want to upload a folder named 'movies' in our 'D' drive then the path that we need to upload is **'/mnt/d/movies'**)

for more:- https://superuser.com/questions/1066261/how-to-access-windows-folders-from-bash-on-ubuntu-on-windows

after this continue with **Usage(Linux and MacOS)**

**All the commands are to be executed in WSL.**

# Usage(Linux and MacOS)
Run the script

    cd uploadit
    python3 main.py

## Uploading

it will ask for the path to folder which is to be uploaded

it will then ask for a raw_path.(this just needs to be a path to an empty directory)

the script will ask for a github token,it will use this token to verify and then push the repos.

this token can be generated by going to Settings->Developer Settings->Personal access tokens-> Generate new tokens and check the repo option as shown below.(Please note that the token generated in the image below,will only be valid for 30 days)

![.](https://github.com/Shwalia/uploadit/blob/master/stuff/token_options.PNG?raw=true)


after the script finishes it will ask for where to put the .map file(Note that this .map file is important and without it your data is as good as lost.),Enter the path to the directory where you want to put this.

## Downloading

While Downloading the script will ask for a .map file and a path to an empty directory

