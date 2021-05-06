# installROS2
Scripts to install ROS2 (dashing) on the NVIDIA Jetson Development Kits

This is a simple script to install ROS2 on the NVIDIA Jetson Development Kits.

In order to run the script:

<blockquote>$ ./installROS2</blockquote>

The script roughly follows the 'Install ROS From Source' procedures from:

<blockquote>https://docs.ros.org/en/dashing/Installation/Ubuntu-Development-Setup.html</blockquote>

Much of the code is taken from the dusty-nv Github repository jetson-containers. The dusty-nv jetson-containers should be used to create a Docker container for the ROS2 on the Jetson. For more information:

<blockquote>
Dockerfile.ros.foxy
https://github.com/dusty-nv/jetson-containers
</blockquote> 

### Testing examples
In one terminal, source the setup file and then run a C++ `talker`:
```
. /opt/ros/dashing/install/local_setup.bash
ros2 run demo_nodes_cpp talker
```
In another terminal source the setup file and then run a Python `listener`:
```
. /opt/ros/dashing/install/local_setup.bash
ros2 run demo_nodes_py listener
```
You should see the `talker` saying that it’s `Publishing` messages and the `listener` saying `I heard those` messages. This verifies both the C++ and Python APIs are working properly. Hooray!

<h3>Notes</h3>
Currently the NVIDIA Jetsons run Ubuntu 18.04. ROS2 dashing requires Ubuntu 18.04.
This is a modification of script in https://github.com/jetsonhacks/installROS2 which installs ROS2 Foxy (which requires Ubuntu 20.04) using workarounds.

<br><p>The file ~/.bashrc is modified using this script; You will want to make sure that the modifications match your expectations. For example, you may have a preference for having the install/setup.bash in another place (i.e. /root/.bashrc).
 

<h3>Release Notes</h3>

<b>May, 2021</b>
* Tested on JetPack 4.5, L4T 32.5
* Tested on Jetson TX2
