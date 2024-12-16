Home Assistant Dynamic Vacuum Control

This repository contains YAML configurations for integrating a robot vacuum (e.g., Roborock) with Home Assistant, allowing for dynamic and customizable room cleaning and mopping. With the included scripts, automations, and input buttons, users can easily select specific rooms to clean or mop and trigger these actions directly from the Home Assistant interface.
Features

    Dynamic Room Selection:
    Use input_boolean entities to select which rooms to clean or mop.
    Button-Controlled Triggers:
    Start cleaning or mopping with a simple button press via input_button entities.
    Room-Specific Automation:
    Automatically send commands to the vacuum to clean or mop only the selected rooms.
    Customizable Cleaning Intensity:
    Adjust cleaning or mopping settings, such as repeat counts or water flow, through Home Assistant inputs.


How It Works

    Room Selection:
    Use the Home Assistant UI to toggle input_boolean entities for the rooms you want to clean or mop.

    Trigger the Action:
    Press the corresponding button (vacuum_rooms or mop_rooms) to initiate the cleaning or mopping process.

    Automation Execution:
    The automation triggers the associated script, which calculates the active rooms and sends commands to the vacuum.

    Completion:
    Once the task is complete, the system resets all toggled rooms and the cleaning repeat count.

Use the 'get maps' action in Home Assistant to get your rooms ID's:

  action: roborock.get_maps
data: {}
target:
  entity_id: vacuum.your_vacuum_id

Repalce the rooms ID's with your own and customise the input booleans to match your room names. 

The scripts set the vacuum to either vacuum only or mop only. 
