# rcj-sim Product Requirements
rcj-sim is a simulation for RoboCup Junior Soccer games.
In brief, it shall be possible for teams to take programs for their
robots and execute these on a virtual robot in a simulated environment
which behaves as similar as possible to the real world.

## Modelling of the robot
As a first step, there must be a way to model the physical construction of
the robot:

- The shape of the robot.
- The positions and mechanical behavior of actuators.
- The positions and behavior of sensors.

Modelable actuators shall include at least:

- Motors with normal wheels.
- Swivel castors.
- Motors with omniwheels.
- An abstract kicker device to model (solenoid or pneumatic) kickers.
- A dribbler.

Modelable sensors shall include at least:

- An abstract range sensor to model e.g. IR/Sonar/Laser range finders.
- A camera.
- An abstract ball range and direction sensor.
- A sideline sensor.
- Rotary encoders for the aforementioned motors.
- An acceleration sensor.
- An abstract global positioning sensor.
- An orientation sensor like a magnetic field sensor.

rcj-sim should support different hardware models for all simulated robots.

## Modelling of the program
There must be a way to take the source code for the real robot's program
and run it in the simulation.
It shall be possible for teams to use a broad range of programming
languages, at least C++.
rcj-sim should support different programs for all simulated robots.
Notably, rcj-sim should be able to support different execution speeds of
the robot programs.

## Modelling of the game
rcj-sim must support at least RoboCup Junior Soccer 2v2 setups, but should
support other setups like 1v1 or games without sidelines as well.

There must be the possibility to simulate enforcement of the game rules.
This includes placing ball and robots on neutral spots, and also counting
scores and resetting the game if a goal is scored.

## User interface
There shall be a visual user interface that can be used to inspect the
progress and state of the simulation.
However, it must be possible to run the simulation without a graphical user
interface.
There must be a interface through which the simulation can be controlled
programmatically, so that rcj-sim can be used for training machine
learning agents.

