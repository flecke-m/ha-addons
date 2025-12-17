# open3e-ha-addon
Home Assistnat Add-on Open3e

Use at your own risk. Please share Feedback to the Addon in the following thread: https://github.com/open3e/open3e/discussions/216 

Note: Removed ARMHF Image as it is not supported anymore by Home Assistant base images for python.

This Add-on connects to a USB Can adapter which is plugged into the Home Assistant device. It runs the Open3e https://github.com/open3e/open3e Can to Mqtt application to read and potentially write to Viessmann E3 platform devices (Heat Pump, Venting System, Solar Inverter etc.)

It requires the Mosquitto MQTT broker to be installed in Home Assistant. It will use the Home Assistant build in capability to publish and subscribe to the MQTT Broker the data comming from the CAN adapter. 

On the configuration only the Topics need to be adjusted if others than the default ones are going to be used:

![Configuration](https://raw.githubusercontent.com/flecke-m/ha-addons/refs/heads/main/open3e/images/homeassistant-configuration1.jpg)

Options:

can: -> should be can0 if not found check network interfaces on your Home Assistant and adjust accordingly
Listen_Topic: -> the topic where the Add-On is listening to commands
Server_Topic: -> the topic where open3e is publishing on
MQTT_FormatString: -> Leave the default option or check the documentation at https://github.com/open3e/open3e for valid options
MQTT_ClientID: -> ClientID how the Add-On shows up in the MQTT Broker

Startup of the Add-On, where initially the command open3e_depictsystem runs:

![Startup](https://raw.githubusercontent.com/flecke-m/ha-addons/refs/heads/main/open3e/images/homeassistant-startup.jpg)


Using the Add-On for Demo purposes with the MQTT-Explorer and sending a command to the Listen_Topic Endpoint and seeing the reply on the open3e Topic:

![Running](https://raw.githubusercontent.com/flecke-m/ha-addons/refs/heads/main/open3e/images/homeassistant-running.jpg)





Please note that Add-ons only work on HAOS and Supervised installations see: https://www.home-assistant.io/installation/ 
