# FairlyRandomSelector

Fairly Random Selector

Generate random, same and fair selection on several computers. 

### Goal

0. Several users using this selector, to get a same random number, each has one computer in front of them. 
Considering the physical unreachable, they need a online dice to help generate the random number *x* appointed by no one. 
0. Several computers run the selector to get the same random number *x*, asynchronous in different place, not influenced by any computer, even if the program is modified - no one can cheat. 
1. Generate a random number *x ~ Uniform(a, b)*, where *a* and *b* is pre-appoint. 
Number *x* subjecting to uniform distribution is guaranteed by python Random module. 

### Requirements & Assumptions

0. No less than 3 users. Two users will make the result determined by the no-host user. 
1. All computers are online, reachable to each other. But all users are unreachable not using this software. 
2. A third-party platform is readable and writeable for all users, and all users have same view to all pages. 

### Model

1. One host is choosen (choosing which computer will not effect the fairness). 
2. All users except the host send a real number to host. Only the sender and host know the number. 
3. After receive all numbers, host post all numbers to the third-party platform. Make sure all users received same posted numbers. 
3. All users add all these number to get a new number *s*. Use number *s* as the seed to get a random number *x*. 
4. Considing using same random generator and same seed, the generated number is exactly same. 
