# impatient-producer

## Problem Description 

A producer sends messages to a consumer for processing. The consumer receives the messages, processes it, and replies back with the same message when it is done.

A message has two fields
  - device-id ( 0 - 255)
  - command ( read, write, open, close)
  
It takes 1-5 seconds to process the message. The processing time depends on the device-id ( processing time = device-id mod 5 ).

The producer sends commands for 10 different devices every time. The producer is impatient, and doesn't wait for a reply before sending new messages. It sends duplicate messages multiple times until a reply has been received for that message.

Consider the cpu is multi-core, and the os is standard linux. Multiple consumers can also be implemented.

The c++ code is provided as an initial framework to understand and to get started with the task. It compiles on linux, though it has many deliberate bugs. One can choose to work on this code as a base or try idependently. One can choose c or rust for implementation as well. 

Please optimize the consumer to handle the impatient producer. Ensure that the code is readable, so that we can understand your thought process.
