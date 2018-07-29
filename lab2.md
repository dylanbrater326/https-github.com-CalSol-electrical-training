# CalSol New Member Training Week 2
##Lab 1.2: BrainTrain and intro to C
* work through the first braintrain lab
* get familiar with coding in C in an embedded environment

## Introduction
Hopefully after last week your computer setup is done, and you're ready to start using it to write code. Most of the code we write, outside of strategy, is called firmware because it interacts more directly with hardware, like being able to read and set the status of various pins on the microcontrollers. It's similar to arduino code if you have any experience with that, just a little more involved. 

Those labs are in a separate repository on our github named braintrain, linked [here] (https://github.com/CalSol/braintrain). When you clone the repository, ensure that the mbed and mbed-scons directories are not empty. If they are, you need to initialize and clone the submodules properly (google to figure out how to do that!) The important files are labeled lab1.md and lab2.md, which have step-by-step instructions for what to do.

## THE LESSON
This week everything that you need to do is in those braintrain labs. You should be given your own (or shared) brain to work on for now, and soldering your own will come later. Get as far as you can, but try to finish the first lab (1.1 to 1.5 or 1.6). If you have questions, google, slack dm's, and other people doing the training are your best friends.

### Code Structure
something.c --> something.bin by running scons. (Try opening a binary in the text editor of your choice. This is close to machine-readable code, but it's very not human-readable.) 

A few tips:
- You don't actually need to know how to read electronics schematics. There are a few circuit diagrams thoughout the lab, but you should be able to guess the point of the circuits.. If you are unsure, get a returning member to help (or read on in the lab and it will be explained). 
- If you've never coded before, we'll be holding a workshop to introduce concepts and help you get started. Look out for an announcement on slack for the time.
- There is a solutions folder. Try your best to not look at it until you've spent at least 10 minutes attempting the problem, or are stuck on a small syntax or otherwise minor issue.