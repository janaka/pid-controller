# node-pid-controller

 Node.js PID controller

A node port of the Arduino PID library intended to be used on the Raspberry Pi

## Installation

      $ npm install pid-controller

## Example

```

var PID = require('pid-controller');

var temp=50;
var ctr = new PID(50, 66, 10,2,1, PID.DIRECT )
ctr.setMode(ctr.AUTOMATIC);
ctr.setTunings(10,2,1);
ctr.setOutputLimits(0,100);
ctr.setInput(temp); 

// 
function checktemp() {
	ctr.compute();
	console.log(ctr);
}

function faketemp() {
	//temp=Math.round((temp+.1));
	if ( temp < 69 ) temp=(temp+.1);
	console.log(temp);
	ctr.setInput(temp); 
}

ctr.compute(); 

setInterval(checktemp, 1000 );
setInterval(faketemp, 700 );

```



## What is a PID Controller?

So, you tell the PID what to measure (the "Input",) Where you want that measurement to be (the "Setpoint",) and the variable to adjust that can make that happen (the "Output".) The PID then adjusts the output trying to make the input equal the setpoint.

## Applied to a self balancing robot examples

Input = current speed and current angle (there will be 2 PID loops).

SetPoint = stationary self balancing robot, speed = 0. Angle setpoint will be the Output from the speed PID

Output = how much to adjust (change speed and/or direction) to get from current angle (input) to desired angle (SetPoint).


## Further documentation

http://playground.arduino.cc/Code/PIDLibrary

http://brettbeauregard.com/blog/2011/04/improving-the-beginners-pid-introduction/


## Author

Rhys Williams
