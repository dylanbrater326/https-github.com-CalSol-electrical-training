# CalSol New Member Training Week 1
## Lab 1.1: Setup and Installation
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

## Git Setup and How to Commit
### Setup
1. clone the respository, you will have to type in your git username and password
```
git clone https://github.com/CalSol/electrical-training.git
```
2. create a new branch, use hyphens or underscores to make life easier
```
git checkout -b <your-name>
```
3. start working :D

### Submit
1. see what files you've changed, confirm that you're on your own branch and not master
```
git status
```
2. add some files to git's tracking
```
git add <name of file>
```
3. commit them
```
git commit -m <message>
```
4. push them to the remote server
```
git push origin <your-branch-name>
```
