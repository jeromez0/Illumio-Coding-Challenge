#### Illumio Coding Challenge
Read a CSV file, given a set of firewall rules, a network packet will be accepted by the firewall if and only if the
direction, protocol, port, and IP address match at least one of the input rules. If a rule contains
a port range, it will match all packets whose port falls within the range. If a rule contains an IP
address range, it will match all packets whose IP address falls within the range.
Your job is to implement a Firewall class, whose interface contains two items:
1. A constructor, taking a single string argument, which is a file path to a CSV file whose contents are as described above,
Note that you do not need to define a static ‘new’ method – simply use the
constructor syntax in the language that you chose.
Remember that you may assume that all content in the input file is valid.
2. A function, accept_packet, that takes exactly four arguments and returns a boolean:
true, if there exists a rule in the file that this object was initialized with that allows traffic
with these particular properties, and false otherwise.


### Problem Solving and Designing a Solution
Writing a constructor that could read and interpret a CSV file would not be too difficult. However, because there could be ranges 
for the port component and for the IP-address component of the CSV file, helper functions would be needed.
I wrote a helper function to add all rules within a port range to a dictionary.
I also wrote a helper function to add all rules within an IP address range to a dictionary. 

Rather than trying to write an algorithm that could calculate a range of an octect for IP Addresses, I simply converted 
the IP address to an integer instead. I then converted the integer back to an IP address. 
I did this using the ipaddress module.


### Running the Code

From the terminal, you can execute the code by inputting the following command:

# python3 main.py

And you will get output with boolean values.

### Refinements

If I had more time, I would run unit tests and timer tests to determine the speed with which my constructor can 
construct the dictionary, with all the rules. I think that the code performs well but it could be slightly faster.
My computer crashed when I tried to include the IP address range from 0.0.0.0 - 255.255.255.255 but the code can handle
65,000 ports easily.

#This project was developed on Linux Ubuntu OS and PyCharm; I have 2 Linux computers at home. One for software development, 
and I have a 4GB Raspberry Pi that is set up to program Arduino controllerboards. Thank you.
