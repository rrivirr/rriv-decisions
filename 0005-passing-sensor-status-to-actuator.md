**Discussion of Structure for Passing Sensor Status to Actuator Drivers**

-  Status: Proposed
- Deciders: @ZavenArra, @jakehosen, @emersonae
- Date 8/12/2022

**Context and Problem Statement**
Future use cases of actuators may need more complex structure than relying on timers to sync up sensors and actuators. More complex actuators may need to know the status of a sensor. Some actuators may be dependent on if a sensor has taken a reading yet or not. 
It was noted that as of now actuators are a “type” of sensor in the waterbear structure, even though actuators don’t “take measurements”. 



**Decision drivers**
- Memory on the waterbear is limited 
- Complexity, time and effort of implementing new structures
  current use cases may not justify the time & effort it would take to implement new structures
- Applicability to multiple types of actuators / use cases
  The solution should be able to be modifiable for different types of actuator drivers


**Considered Options**
- Creating a counter structure for sensors
	this solution would likely be implemented in both of the following options : 

- Passing sensor parameters to the actuator driver
	private variables would hold info on where in the reading cycle a sensor is 
	these variables would be passed as parameters to functions of the actuator 
	Examples: if the sensor has warmed up, where in the individual reading cycle a sensor is, and how many readings have been completed.

- Creating a super class of sensors and actuators
	actuators shouldn’t stay a type of sensor because a lot of the structure of a sensor class, an actuator doesn’t use
	This generally is a good idea because both sensors and actuators use “slots” on the water bear. 

	


**Decision Outcome**

Chosen : passing sensor data to the actuator driver 

Positive consequences
This solution doesn’t change the structure of actuators and sensors too much. 

Negative consequences
There might not be enough space in the structure of actuator drivers for all the sensor variables
This solution does not allow for a way to actuators to know where in the larger measurement cycle the datalogger is in. However the datalogger structure shouldn’t be changed significantly.



**Pros and cons of the options**

The other proposed solutions may need to be implemented in addition to the chosen decision. 

