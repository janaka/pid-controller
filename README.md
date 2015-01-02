# node-pid-controller

 Node.js PID controller

A node port of the Arduino PID library intended to be used on the Raspberry Pi

## Installation

      $ npm install pid-controller

## Example
please see test.js



## What is a PID Controller?

So, you tell the PID what to measure (the "Input",) Where you want that measurement to be (the "Setpoint",) and the variable to adjust that can make that happen (the "Output".) The PID then adjusts the output trying to make the input equal the setpoint.

## Applied to a self balancing robot examples

Input = current speed and current angle (there will be 2 PID loops).

SetPoint = stationary self balancing robot, speed = 0. Angle setpoint will be the Output from the speed PID

Output = how much to adjust (change speed and/or direction) to get from current angle (input) to desired angle (SetPoint).


## Further documentation

http://playground.arduino.cc/Code/PIDLibrary


## Author

Rhys Williams
