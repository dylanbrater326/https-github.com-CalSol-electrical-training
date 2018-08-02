# CalSol New Member Training 2.2
## Lab 2.2: BRAIN Train part 2 
* introduce communication between boards and CAN
* get familiar with debugging tools

## Introduction
Last week you hopefully got used to coding in C and how embedded programming works. You won't feel completely comfortable with the new language or style, but that's expected and you have (hopefully) much more time to get used to the difference. This week, we'll dive into a very important part of our car: communication.

## THE LESSON
CAN, or a Controller Area Network, is the bus that we've chosen to use in our car. It's standard in a lot of actual cars, has a reasonably high bandwidth, and relatively easy to use and debug. Because we have many smaller boards that all do their own processing (if you want to learn more about why, ask a returning member), communication between all of the different circuits is vital to our car function. 

The real purpose of this lab is to force you guys to make friends.

Really though, during the lab time you sign up for, be ready to have to interact with someone new or be a party pooper and bring a friend to work with. Go through the lab together and help each other out if one of you gets stuck.

### Notes
- There' a ton of documentation and articles online about CAN, if you're curious about learning more. I've linked a couple good introductory articles [here] (https://www.kvaser.com/about-can/the-can-protocol/can-messages-33/) and [here] (https://www.csselectronics.com/screen/page/simple-intro-to-can-bus/language/en) , and Wikipedia [here] (https://en.wikipedia.org/wiki/CAN_bus) because it's usually pretty good.