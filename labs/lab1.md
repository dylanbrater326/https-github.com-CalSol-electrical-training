# CalSol Electrical Workshop
## Lab 1: Setup and Installation
* Start learning how to use Git
* Get access to Slack, Git, Google Drive, Trello, and the wiki
* Get your laptop set up to write firmware

## Introduction
Welcome to CalSol! We're the electrical subteam on Berkeley's Solar Car team, and over the next few weeks you'll learn about what the club and the team does. Hopefully you got the quick intro during the general meeting and electrical meeting, but if not or you ever have any questions ask any returning member in person or on slack. Everyone is welcome join regardless of prior experience, and you're also free to try out other subteams and explore to see what interests you the most.

Over most of the next semester, you'll be doing a series of labs like this one that guide you through the essentials of electrical. Most are designed to be completed in one week, but the time it takes will depend on your skill level. No worries if a lab takes you three weeks or you breeze through four in one week, we'll do our best to accomodate everyone. See the main git repository for a general overview of the weeks.

## Most Important Facts
Weekly meetings
* general meetings Monday 7-9 pm third floor, Jacobs
* electrical meetings Thursday 7-8 pm Supernode, Cory

## Format
Every week or so, a short (15 min or less) lecture will introduce the focus of the lab and give you essential information and a place to get started. Each lab will have a goal and some sort of end product as a goal, which you will be submitting to your brainch of the electrical-training repository on CalSol's github when you finish. This is mainly to help you get comfortable with git, but also so we can keep track of how everyone is doing. We will have "office hours" when you can come by and ask for help, based on the lab that you're working on.

## THE LESSON PT 1
### Computer Setup
The goal this week is to set up the toolchain that we use for compiling and building our firmware. Firmware is the name of all of the C code that runs on the various chips throughout the car, whether that be the Battery Management System, the front Lights Controller, or the Pedal Board. Our toolchain has 3 main components: GCC-ARM, SCons, and OpenOCD. GCC-ARM is the compiler that builds files compatable with the architecture of our microcontrollers, different from the x86 that probably runs on your laptop. SCons is a build system similar to Make or Automake that makes building a complex project with many dependencies easier, and OpenOCD helps with flashing and debugging. If you want to learn more about any of these tools specifically, Google is a great resource, but feel free to ask any returning member if you have questions. 

If you are running Linux or OSX, follow the instructions [here](https://github.com/CalSol/Tachyon-FW) by scrolling down to the README and use brew, apt, or the appropriate package manager. For Windows, the process is more complicated and involves more than typing 5 lines into terminal. The link should give you step by step instructions on what to download, follow directions and ask for help if something doesn't add up. Don't worry about the Eclipse part of the setup unless you really want to the IDE to code, the plug-ins can be a little finicky. The alterative is to use whatever text editor you want, from Sublime to Atom to Vim to Notepad++.
 
Your goal for the week is to have everything set up, clone the firmware repository on git, and be able to build it by runing scons. The next part of the readme guides you through cloning the Tachyon-FW repository on git, and once you have a local copy you should be able to run the command
```
scons
```
to build all of the files. Once it works without erroring, take a screenshot of your terminal output, and that will be what you submit for your first lab's work! To do so, you will clone the electrical-training repository, make your own branch, and push your picture.

### Hardware
The last think that you need is KiCAD. You can find that [here](http://kicad-pcb.org/download/), and just follow the instructions for whatever description fits your computer. Also clone the Tachyon-HW repository on github.


### Git Setup and How to Commit

Setup:
1. clone the respository, you will have to type in your git username and password. Use the Desktop gui, or type this into your terminal
```
git clone https://github.com/CalSol/electrical-training.git
```
2. create a new branch in the electrical-training repository, use hyphens or underscores to make life easier
```
git checkout -b <your-name>
```
3. start working :D

To Submit:
1. see what files you've changed, confirm that you're on your own branch and not master
```
git status
```
2. add some files to git's staging system 
```
git add <name of file>
```
3. commit them to be ready to be pushed
```
git commit -m <message>
```
4. push them to the remote server
```
git push origin <your-branch-name>
```

## Conclusion
And that's it for the first week's lab! Please fill out our anonymous feedback form, and be ready to start writing c next week :)