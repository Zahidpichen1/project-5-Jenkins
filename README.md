# Introduction to Jenkins

## Description
Learning the basics of **Jenkins** with the help of flask library, we created a simple hello world flask app and tested it in Jenkins.

## Steps

### Building Files
1) app.py: which has flask code
2) requirements.txt: which has the required library names
3) JenkinFile: which contains the commands to be run in Jenkins
3) test_app.py: which contains the code to test *app.py* file

### Git & Other Commands used in Command Prompt
1) `mkdir <file_name>` to create the folder
2) `cd <file name>` to go inside the folder
3) `git init`, initializing folder as git repository
4) manually add all the files
5) `git add .` to add all the files into git track
6) `git commit -m "<message>"`, it commits whatever is there in the track
7) `git remote add origin <GitHub repository link>`, builds connection between git and github
8) `git push --set-upstream origin master`, sends all the files from git to github.


### Jenkins
1) created a new item with item name as **9. Counsumer forcast prediction**
2) selected *Pipeline* as the item type
3) selected *GitHub hook trigger for GITScm polling* in **Build Triggers**
4) selected *Pipline script from SCM* in **Pipeline**
5) added the GitHub repository link
6) double checked Script Path name is the same in Jenkins and GitHub
7) Saved the Configurations
8) Clicked build now

#### Output
  ![4](https://github.com/user-attachments/assets/dfb7aac9-2e51-44d7-840f-c1813f896a6f)
