# ur_robot_driver

The new driver for Universal Robots UR3, UR5 and UR10 robots with CB3 controllers and the e-series.

## Launchfiles
### ur3e_bringup.launch

Standalone launchfile to startup a ur3e. This requires a robot reachable via a network connection.

#### Arguments
 * "**controller_config_file**" (default: "$(find ur_robot_driver)/config/ur3e_controllers.yaml")

    Config file used for defining the ROS-Control controllers.

 * "**controllers**" (default: "joint_state_controller scaled_pos_traj_controller speed_scaling_state_controller force_torque_sensor_controller")

    Controllers that are activated by default.

 * "**debug**" (default: "false")

    Debug flag that will get passed on to ur_common.launch

 * "**headless_mode**" (default: "false")

    Automatically send URScript to robot to execute. On e-Series this does require the robot to be in 'remote-control' mode. With this, the URCap is not needed on the robot.

 * "**kinematics_config**" (default: "$(find ur_e_description)/config/ur3e_default.yaml")

    Kinematics config file used for calibration correction. This will be used to verify the robot's calibration is matching the robot_description.

 * "**limited**" (default: "false")

    Use the description in limited mode (Every axis rotates from -PI to PI)

 * "**robot_description_file**" (default: "$(find ur_e_description)/launch/ur3e_upload.launch")

    Robot description launch file.

 * "**robot_ip**" (Required)

    IP address by which the robot can be reached.

 * "**stopped_controllers**" (default: "pos_traj_controller")

    Controllers that are initally loaded, but not started.

 * "**tf_prefix**" (default: "")

    tf_prefix used for the robot.

 * "**tool_baud_rate**" (default: "115200")

    Baud rate used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_device_name**" (default: "/tmp/ttyUR")

    Local device name used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_parity**" (default: "0")

    Parity configuration used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_rx_idle_chars**" (default: "1.5")

    Number of idle chars in RX channel used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_stop_bits**" (default: "1")

    Number of stop bits used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_tcp_port**" (default: "54321")

    Port on which the robot controller publishes the tool comm interface. Only used, when `use_tool_communication` is set to true.

 * "**tool_tx_idle_chars**" (default: "3.5")

    Number of idle chars in TX channel used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_voltage**" (default: "0")

    Tool voltage set at the beginning of the UR program. Only used, when `use_tool_communication` is set to true.

 * "**use_tool_communication**" (default: "false")

    On e-Series robots tool communication can be enabled with this argument

### ur10_bringup.launch

Standalone launchfile to startup a ur10 robot. This requires a robot reachable via a network connection.

#### Arguments
 * "**controller_config_file**" (default: "$(find ur_robot_driver)/config/ur10_controllers.yaml")

    Config file used for defining the ROS-Control controllers.

 * "**controllers**" (default: "joint_state_controller scaled_pos_traj_controller speed_scaling_state_controller force_torque_sensor_controller")

    Controllers that are activated by default.

 * "**debug**" (default: "false")

    Debug flag that will get passed on to ur_common.launch

 * "**headless_mode**" (default: "false")

    Automatically send URScript to robot to execute. On e-Series this does require the robot to be in 'remote-control' mode. With this, the URCap is not needed on the robot.

 * "**kinematics_config**" (default: "$(find ur_description)/config/ur10_default.yaml")

    Kinematics config file used for calibration correction. This will be used to verify the robot's calibration is matching the robot_description.

 * "**limited**" (default: "false")

    Use the description in limited mode (Every axis rotates from -PI to PI)

 * "**robot_description_file**" (default: "$(find ur_description)/launch/ur10_upload.launch")

    Robot description launch file.

 * "**robot_ip**" (Required)

    IP address by which the robot can be reached.

 * "**stopped_controllers**" (default: "pos_traj_controller")

    Controllers that are initally loaded, but not started.

 * "**tf_prefix**" (default: "")

    tf_prefix used for the robot.

### ur_control.launch

Robot bringup launchfile without the robot description. Include this, if you want to include robot control into a larger launchfile structure.

#### Arguments
 * "**controller_config_file**" (Required)

    Config file used for defining the ROS-Control controllers.

 * "**controllers**" (default: "joint_state_controller scaled_pos_traj_controller speed_scaling_state_controller force_torque_sensor_controller")

    Controllers that are activated by default.

 * "**debug**" (default: "false")

    If set to true, will start the driver inside gdb

 * "**headless_mode**" (default: "false")

    Automatically send URScript to robot to execute. On e-Series this does require the robot to be in 'remote-control' mode. With this, the URCap is not needed on the robot.

 * "**kinematics_config**" (Required)

    Kinematics config file used for calibration correction. This will be used to verify the robot's calibration is matching the robot_description. Pass the same config file that is passed to the robot_description.

 * "**launch_prefix**" (Required)

    Please add description. See file "launch/ur_control.launch".

 * "**robot_ip**" (Required)

    IP address by which the robot can be reached.

 * "**rtde_input_recipe_file**" (default: "$(find ur_robot_driver)/resources/rtde_input_recipe.txt")

    Recipe file used for the RTDE-inputs. Only change this if you know what you're doing.

 * "**rtde_output_recipe_file**" (default: "$(find ur_robot_driver)/resources/rtde_output_recipe.txt")

    Recipe file used for the RTDE-outputs. Only change this if you know what you're doing.

 * "**stopped_controllers**" (default: "pos_traj_controller")

    Controllers that are initally loaded, but not started.

 * "**tf_prefix**" (default: "")

    tf_prefix used for the robot.

 * "**tool_baud_rate**" (default: "115200")

    Baud rate used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_device_name**" (default: "/tmp/ttyUR")

    Local device name used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_parity**" (default: "0")

    Parity configuration used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_rx_idle_chars**" (default: "1.5")

    Number of idle chars in RX channel used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_stop_bits**" (default: "1")

    Number of stop bits used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_tcp_port**" (default: "54321")

    Port on which the robot controller publishes the tool comm interface. Only used, when `use_tool_communication` is set to true.

 * "**tool_tx_idle_chars**" (default: "3.5")

    Number of idle chars in TX channel used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_voltage**" (default: "0")

    Tool voltage set at the beginning of the UR program. Only used, when `use_tool_communication` is set to true.

 * "**urscript_file**" (default: "$(find ur_robot_driver)/resources/servoj.urscript")

    Path to URScript that will be sent to the robot and that forms the main control program.

 * "**use_tool_communication**" (Required)

    On e-Series robots tool communication can be enabled with this argument

### ur_common.launch

Launchfile that starts a robot description with robot_state publisher and the driver for a given robot. It is recommended to use the individual launch files instead such as `ur10_bringup.launch`. Additionally, this launchfile can be used as a template to include this driver into a larger launch file structure.

#### Arguments
 * "**controller_config_file**" (Required)

    Config file used for defining the ROS-Control controllers.

 * "**controllers**" (default: "joint_state_controller scaled_pos_traj_controller speed_scaling_state_controller force_torque_sensor_controller")

    Controllers that are activated by default.

 * "**debug**" (default: "false")

    Debug flag that will get passed on to ur_control.launch

 * "**headless_mode**" (default: "false")

    Automatically send URScript to robot to execute. On e-Series this does require the robot to be in 'remote-control' mode. With this, the URCap is not needed on the robot.

 * "**kinematics_config**" (Required)

    Kinematics config file used for calibration correction. This will be used to verify the robot's calibration is matching the robot_description.

 * "**limited**" (default: "false")

    Use the description in limited mode (Every axis rotates from -PI to PI)

 * "**robot_description_file**" (Required)

    Robot description launch file.

 * "**robot_ip**" (Required)

    IP address by which the robot can be reached.

 * "**stopped_controllers**" (default: "pos_traj_controller")

    Controllers that are initally loaded, but not started.

 * "**tf_prefix**" (default: "")

    tf_prefix used for the robot.

 * "**tool_baud_rate**" (default: "115200")

    Baud rate used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_device_name**" (default: "/tmp/ttyUR")

    Local device name used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_parity**" (default: "0")

    Parity configuration used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_rx_idle_chars**" (default: "1.5")

    Number of idle chars in RX channel used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_stop_bits**" (default: "1")

    Number of stop bits used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_tcp_port**" (default: "54321")

    Port on which the robot controller publishes the tool comm interface. Only used, when `use_tool_communication` is set to true.

 * "**tool_tx_idle_chars**" (default: "3.5")

    Number of idle chars in TX channel used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_voltage**" (default: "0")

    Tool voltage set at the beginning of the UR program. Only used, when `use_tool_communication` is set to true.

 * "**use_tool_communication**" (Required)

    On e-Series robots tool communication can be enabled with this argument

### ur5_bringup.launch

Standalone launchfile to startup a ur5 robot. This requires a robot reachable via a network connection.

#### Arguments
 * "**controller_config_file**" (default: "$(find ur_robot_driver)/config/ur5_controllers.yaml")

    Config file used for defining the ROS-Control controllers.

 * "**controllers**" (default: "joint_state_controller scaled_pos_traj_controller speed_scaling_state_controller force_torque_sensor_controller")

    Controllers that are activated by default.

 * "**debug**" (default: "false")

    Debug flag that will get passed on to ur_common.launch

 * "**headless_mode**" (default: "false")

    Automatically send URScript to robot to execute. On e-Series this does require the robot to be in 'remote-control' mode. With this, the URCap is not needed on the robot.

 * "**kinematics_config**" (default: "$(find ur_description)/config/ur5_default.yaml")

    Kinematics config file used for calibration correction. This will be used to verify the robot's calibration is matching the robot_description.

 * "**limited**" (default: "false")

    Use the description in limited mode (Every axis rotates from -PI to PI)

 * "**robot_description_file**" (default: "$(find ur_description)/launch/ur5_upload.launch")

    Robot description launch file.

 * "**robot_ip**" (Required)

    IP address by which the robot can be reached.

 * "**stopped_controllers**" (default: "pos_traj_controller")

    Controllers that are initally loaded, but not started.

 * "**tf_prefix**" (default: "")

    tf_prefix used for the robot.

### ur5e_bringup.launch

Standalone launchfile to startup a ur5e robot. This requires a robot reachable via a network connection.

#### Arguments
 * "**controller_config_file**" (default: "$(find ur_robot_driver)/config/ur5e_controllers.yaml")

    Config file used for defining the ROS-Control controllers.

 * "**controllers**" (default: "joint_state_controller scaled_pos_traj_controller speed_scaling_state_controller force_torque_sensor_controller")

    Controllers that are activated by default.

 * "**debug**" (default: "false")

    Debug flag that will get passed on to ur_common.launch

 * "**headless_mode**" (default: "false")

    Automatically send URScript to robot to execute. On e-Series this does require the robot to be in 'remote-control' mode. With this, the URCap is not needed on the robot.

 * "**kinematics_config**" (default: "$(find ur_e_description)/config/ur5e_default.yaml")

    Kinematics config file used for calibration correction. This will be used to verify the robot's calibration is matching the robot_description.

 * "**limited**" (default: "false")

    Use the description in limited mode (Every axis rotates from -PI to PI)

 * "**robot_description_file**" (default: "$(find ur_e_description)/launch/ur5e_upload.launch")

    Robot description launch file.

 * "**robot_ip**" (Required)

    IP address by which the robot can be reached.

 * "**stopped_controllers**" (default: "pos_traj_controller")

    Controllers that are initally loaded, but not started.

 * "**tf_prefix**" (default: "")

    tf_prefix used for the robot.

 * "**tool_baud_rate**" (default: "115200")

    Baud rate used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_device_name**" (default: "/tmp/ttyUR")

    Local device name used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_parity**" (default: "0")

    Parity configuration used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_rx_idle_chars**" (default: "1.5")

    Number of idle chars in RX channel used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_stop_bits**" (default: "1")

    Number of stop bits used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_tcp_port**" (default: "54321")

    Port on which the robot controller publishes the tool comm interface. Only used, when `use_tool_communication` is set to true.

 * "**tool_tx_idle_chars**" (default: "3.5")

    Number of idle chars in TX channel used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_voltage**" (default: "0")

    Tool voltage set at the beginning of the UR program. Only used, when `use_tool_communication` is set to true.

 * "**use_tool_communication**" (default: "false")

    On e-Series robots tool communication can be enabled with this argument

### ur3_bringup.launch

Standalone launchfile to startup a ur5 robot. This requires a robot reachable via a network connection.

#### Arguments
 * "**controller_config_file**" (default: "$(find ur_robot_driver)/config/ur3_controllers.yaml")

    Config file used for defining the ROS-Control controllers.

 * "**controllers**" (default: "joint_state_controller scaled_pos_traj_controller speed_scaling_state_controller force_torque_sensor_controller")

    Controllers that are activated by default.

 * "**debug**" (default: "false")

    Debug flag that will get passed on to ur_common.launch

 * "**headless_mode**" (default: "false")

    Automatically send URScript to robot to execute. On e-Series this does require the robot to be in 'remote-control' mode. With this, the URCap is not needed on the robot.

 * "**kinematics_config**" (default: "$(find ur_description)/config/ur3_default.yaml")

    Kinematics config file used for calibration correction. This will be used to verify the robot's calibration is matching the robot_description.

 * "**limited**" (default: "false")

    Use the description in limited mode (Every axis rotates from -PI to PI)

 * "**robot_description_file**" (default: "$(find ur_description)/launch/ur3_upload.launch")

    Robot description launch file.

 * "**robot_ip**" (Required)

    IP address by which the robot can be reached.

 * "**stopped_controllers**" (default: "pos_traj_controller")

    Controllers that are initally loaded, but not started.

 * "**tf_prefix**" (default: "")

    tf_prefix used for the robot.

### ur10e_bringup.launch

Standalone launchfile to startup a ur10e robot. This requires a robot reachable via a network connection.

#### Arguments
 * "**controller_config_file**" (default: "$(find ur_robot_driver)/config/ur10e_controllers.yaml")

    Config file used for defining the ROS-Control controllers.

 * "**controllers**" (default: "joint_state_controller scaled_pos_traj_controller speed_scaling_state_controller force_torque_sensor_controller")

    Controllers that are activated by default.

 * "**debug**" (default: "false")

    Debug flag that will get passed on to ur_common.launch

 * "**headless_mode**" (default: "false")

    Automatically send URScript to robot to execute. On e-Series this does require the robot to be in 'remote-control' mode. With this, the URCap is not needed on the robot.

 * "**kinematics_config**" (default: "$(find ur_e_description)/config/ur10e_default.yaml")

    Kinematics config file used for calibration correction. This will be used to verify the robot's calibration is matching the robot_description.

 * "**limited**" (default: "false")

    Use the description in limited mode (Every axis rotates from -PI to PI)

 * "**robot_description_file**" (default: "$(find ur_e_description)/launch/ur10e_upload.launch")

    Robot description launch file.

 * "**robot_ip**" (Required)

    IP address by which the robot can be reached.

 * "**stopped_controllers**" (default: "pos_traj_controller")

    Controllers that are initally loaded, but not started.

 * "**tf_prefix**" (default: "")

    tf_prefix used for the robot.

 * "**tool_baud_rate**" (default: "115200")

    Baud rate used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_device_name**" (default: "/tmp/ttyUR")

    Local device name used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_parity**" (default: "0")

    Parity configuration used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_rx_idle_chars**" (default: "1.5")

    Number of idle chars in RX channel used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_stop_bits**" (default: "1")

    Number of stop bits used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_tcp_port**" (default: "54321")

    Port on which the robot controller publishes the tool comm interface. Only used, when `use_tool_communication` is set to true.

 * "**tool_tx_idle_chars**" (default: "3.5")

    Number of idle chars in TX channel used for tool communication. Only used, when `use_tool_communication` is set to true.

 * "**tool_voltage**" (default: "0")

    Tool voltage set at the beginning of the UR program. Only used, when `use_tool_communication` is set to true.

 * "**use_tool_communication**" (default: "false")

    On e-Series robots tool communication can be enabled with this argument

## Nodes
### ur_robot_driver_node

This is the actual driver node containing the ROS-Control stack. Interfaces documented here refer to the robot's hardware interface. Controller-specific API elements might be present for the individual controllers outside of this package.

#### Advertised Services
 * "**hand_back_control**" ([std_srvs/Trigger](http://docs.ros.org/api/std_srvs/html/srv/Trigger.html))

    Calling this service will make the "External Control" program node on the UR-Program return.

 * "**resend_robot_program**" ([std_srvs/Trigger](http://docs.ros.org/api/std_srvs/html/srv/Trigger.html))

    When in headless mode, this sends the URScript program to the robot for execution. Use this after the program has been interrupted, e.g. by a protective- or EM-stop.

 * "**set_io**" (ur_msgs/SetIO)

    Service to set any of the robot's IOs

 * "**set_speed_slider**" (ur_msgs/SetSpeedSliderFraction)

    Set the speed slider fraction used by the robot's execution. Values should be between 0 and 1. Only set this smaller than 1 if you are using the scaled controllers (as by default) or you know what you're doing. Using this with other controllers might lead to unexpected behaviors.

#### Parameters
 * "**hardware_interface/joints**" (Required)

    Names of the joints. Usually, this is given in the controller config file.

 * "**headless_mode**" (Required)

    Start robot in headless mode. This does not require the 'External Control' URCap to be running on the robot, but this will send the URScript to the robot directly. On e-Series robots this requires the robot to run in 'remote-control' mode.

 * "**input_recipe_file**" (Required)

    Path to the file containing the recipe used for requesting RTDE inputs.

 * "**kinematics/hash**" (Required)

    Hash of the calibration reported by the robot. This is used for validating the robot description is using the correct calibration. If the robot's calibration doesn't match this hash, an error will be printed. You can use the robot as usual, however Cartesian poses of the endeffector might be inaccurate. See the "ur_calibration" package on help how to generate your own hash matching your actual robot.

 * "**output_recipe_file**" (Required)

    Path to the file containing the recipe used for requesting RTDE outputs.

 * "**robot_ip**" (Required)

    The robot's IP address.

 * "**script_file**" (Required)

    Path to the urscript code that will be sent to the robot.

 * "**tf_prefix**" (default: "")

    Please add description. See hardware_interface.cpp line number: 67



    	robot_hw_nh.param<std::string>("tf_prefix", tf_prefix_, "");

 * "Symbol: **this_thread**" (default: "&params")

    Please add description. See hardware_interface_node.cpp line number: 98



    	int ret = pthread_setschedparam(this_thread, SCHED_FIFO, &params);

 * "**tool_baud_rate**" (Required)

    Baud rate used for tool communication. Will be set as soon as the UR-Program on the robot is started. See UR documentation for valid baud rates.  Note: This parameter is only evaluated, when the parameter "use_tool_communication" is set to TRUE.  Then, this parameter is required.

 * "**tool_parity**" (Required)

    Parity used for tool communication. Will be set as soon as the UR-Program on the robot is started. Can be 0 (None), 1 (odd) and 2 (even).  Note: This parameter is only evaluated, when the parameter "use_tool_communication" is set to TRUE.  Then, this parameter is required.

 * "**tool_rx_idle_chars**" (Required)

    Number of idle chars for the RX unit used for tool communication. Will be set as soon as the UR-Program on the robot is started. Valid values: min=1.0, max=40.0  Note: This parameter is only evaluated, when the parameter "use_tool_communication" is set to TRUE.  Then, this parameter is required.

 * "**tool_stop_bits**" (Required)

    Number of stop bits used for tool communication. Will be set as soon as the UR-Program on the robot is started. Can be 1 or 2.  Note: This parameter is only evaluated, when the parameter "use_tool_communication" is set to TRUE.  Then, this parameter is required.

 * "**tool_tx_idle_chars**" (Required)

    Number of idle chars for the TX unit used for tool communication. Will be set as soon as the UR-Program on the robot is started. Valid values: min=0.0, max=40.0  Note: This parameter is only evaluated, when the parameter "use_tool_communication" is set to TRUE.  Then, this parameter is required.

 * "**tool_voltage**" (Required)

    Tool voltage that will be set as soon as the UR-Program on the robot is started. Note: This parameter is only evaluated, when the parameter "use_tool_communication" is set to TRUE. Then, this parameter is required.

 * "**use_tool_communication**" (Required)

    Should the tool's RS485 interface be forwarded to the ROS machine? This is only available on e-Series models. Setting this parameter to TRUE requires multiple other parameters to be set,as well.

#### Published topics
 * "**robot_program_running**" ([std_msgs/Bool](http://docs.ros.org/api/std_msgs/html/msg/Bool.html))

    Whenever the runtime state of the "External Control" program node in the UR-program changes, a message gets published here. So this is equivalent to the information whether the robot accepts commands from ROS side.

#### Subscribed topics
 * "**script_command**" ([std_msgs/String](http://docs.ros.org/api/std_msgs/html/msg/String.html))

    Send arbitrary script commands to this topic. Note: On e-Series the robot has to be in remote-control mode.  Sending scripts to this will stop program execution unless wrapped in a secondary program:  sec myProgram(): set_digital_out(0, True) end

### tool_communication

This node is used to start the RS485 tunneling interface on the ROS machine. This requires that the RS485 daemon is running on the robot controller and tool communication is enabled on the robot.

#### Parameters
 * "**~device_name**" (Required)

    By default, socat will create a pty in /dev/pts/N with n being an increasing number. Additionally, a symlink at the given location will be created. Use an absolute path here.

 * "**~robot_ip**" (Required)

    IP address of the robot

 * "**~tcp_port**" (default: "54321")

    Port on which the remote pc (robot) publishes the interface

