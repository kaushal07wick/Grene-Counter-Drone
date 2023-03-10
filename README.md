# Grene-Counter-Drone using FastPlanner and Octomap

Download mavros, mavlink and Px4-Autopilot from their respective Github repo

## Catkin Folder Structure
All folder(workspaces) are in /home directory
1. PX4-Autopilot\
  Contains PX4-Gazebo-SITL
 
2. catkin_ws\
  Contains mavros
  
3. fastplanner_ws\
  Contains mapping, planning and controller nodes


## Running the Simulation

### Terminal 1:-
```bash
cd PX4-Autopilot/
roslaunch px4 mavros_posix_sitl.launch
```

In the same terminal type
```bash
pxh> commander takeoff
```

It will launch Gazebo, World, Mavros, PX4, Quadcopter(iris_depth_camera)

### Terminal 2:-
```bash
cd fastplanner_ws/
source devel/setup.bash
roslaunch FastPlannerOctomap MappingSim.launch
```
Give goal location using 2D Nav Goal option in  the rviz

### Terminal 3:-
```bash
cd fastplanner_ws/
source devel/setup.bash
rosrun FastPlannerOctomap Planner
```
For the startOver option select either 1 or 0\
Also give the height (in metres) of the goal location when prompted.

### Terminal 4:-
```bash
cd fastplanner_ws/
source devel/setup.bash
rosrun FastPlannerOctomap Controller
```
