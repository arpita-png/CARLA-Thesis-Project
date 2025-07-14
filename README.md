# Objective-
To improve vehicle recovery and decision-making in edge-case scenarios using V2X communication (Vehicle-to-Vehicle and Vehicle-to-Infrastructure) in the CARLA Simulator.

# Requirements
- CARLA Simulator v0.9.15
- Python 
- Jupyter Notebook

classes, objects, methods, attributes 

A Python virtual environment (carla_jupyter_env) was created to run CARLA simulations and interact with them through Jupyter Notebooks.

CARLA uses a client-server architecture.<br>
The server runs the simulation.<br>
The client (python script) uses the API to interact with it.<br>
The CARLA server = the actual simulator window running in Unreal Engine.<br>
Python code = the client that sends instructions to control the simulation.<br>

# CARLA Simulator
It's the program running in the background (to launch ./CarlaUE4.sh).<br>
It is separate from the Python script.<br>
It handles the visual world, physics, cars, pedestrians, traffic lights, weather, etc.<br>
When the script says "spawn a car", this simulator adds that car to the 3D scene<br>

# CARLA Communication Flow Diagram
-Python script wants to talk to CARLA<br>
-use carla.Client('localhost', 2000) to create a client — a connection.  client object-client is the connection object to the CARLA simulator created by client = carla.Client()<br>
-The client object becomes the controller that sends commands to CARLA.<br>
-CARLA simulator is already running (in its Unreal Engine window).<br>
-CARLA simulator executes command (e.g., spawns the car), updates the world.<br>
-sends data back (e.g., car location, camera image)<br>
-Python Script (receives and continues)<br>

















