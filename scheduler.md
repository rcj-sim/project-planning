# Scheduler
There must be a central scheduler which updates the robots, the refree
program and the physics simulation.

In order to implement the requirement that the robot programs can run at
different speeds, the robot program will need to signal how much time has
passed at suitable times, e. g. after every pass of the main loop.

The world will be regularly updated at a certain interval, e. g. every
0.05 seconds.

Example:
If the robot is updated directly after the world update at time T, and it
tells the scheduler that the execution of the update took 10 ms, the
scheduler will run another robot update at T+10ms.
If this second update takes 100ms, then the scheduler will update the
world at T+50ms and at T+100ms before updating the robot at T+110ms.

This makes it possible to have every agent running in its own separate
thread.
What is important here is that the robot programs have a dependency on the
world state.
That means that before the world may be updated, all robots must have set
the time point of their next update.
It also means that the world cannot be updated while robot threads are
running.
A solution to this could be copy on write for the world object positions,
but this seems too complicated right now.

