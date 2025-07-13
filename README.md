# OBJECTIVE-
To improve vehicle recovery and decision-making in edge-case scenarios using V2X communication (Vehicle-to-Vehicle and Vehicle-to-Infrastructure) in the CARLA Simulator.

# Requirements
- CARLA Simulator v0.9.15
- Python 
- Jupyter Notebook

classes, objects, methods, attributes 

A Python virtual environment (carla_jupyter_env) was created to run CARLA simulations and interact with them through Jupyter Notebooks.

CARLA uses a client-server architecture
The server runs the simulation
The client (python script) uses the API to interact with it
The CARLA server = the actual simulator window running in Unreal Engine.
Python code = the client that sends instructions to control the simulation.

# CARLA Simulator?
It's the program running in the background (usually started with ./CarlaUE4.sh).
It is separate from the Python script.
It handles the visual world, physics, cars, pedestrians, traffic lights, weather, etc.
When the script says "spawn a car", this simulator adds that car to the 3D scene

# CARLA Communication Flow Diagram
-Python script wants to talk to CARLA
-use carla.Client('localhost', 2000) to create a client — a connection.  client object-client is the connection object to the CARLA simulator created by client = carla.Client()
-The client object becomes the controller that sends commands to CARLA.
-CARLA simulator is already running (in its Unreal Engine window).
-CARLA simulator executes command (e.g., spawns the car), updates the world.
-sends data back (e.g., car location, camera image)
-Python Script (receives and continues)

# client = carla.Client('localhost', 2000) --creates a communication channel between your script and the CARLA simulator.
'localhost':
- “connect to a CARLA simulator that is running on this computer.”
-If the simulator was running on a remote machine, use its IP address (e.g., '192.168.1.42').
2000: 
CARLA simulator running on port 2000, this is the TCP port number that CARLA uses by default.
The simulator listens on this port for incoming Python API commands.
