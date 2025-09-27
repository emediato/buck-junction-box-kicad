## junction box kicad
pcb with esp32

# Schematics

![schematics](https://github.com/user-attachments/assets/bfc248f8-e326-4082-8cb7-8f14c0574b9b)


![schematicospB](https://github.com/user-attachments/assets/29c07a3e-795b-4e6d-af77-6db05fbfbee0)


# power plant

![Capture](https://github.com/user-attachments/assets/400b17b4-2393-4028-81d6-9d8e0ed5f4ea)


Hardware design knowledge .
1. While designing with ethernet 10/100/1000 speed we need to keep the following in mind as below.
2. Ethernet needs esd protection
3. RJ45 port will need EMI filters
4. Ethernet TX and RX pairs need to be impedance matched lines.
5. Shorter traces will provide better emi immunity.
6. We will need an Ethernet PHY interface chip
7. PHY data input lines need series resistors for reflection arrest.
8. Length Matched RX TX pair will improve the link quality and reliability.


https://www.st.com/resource/en/datasheet/l298.pdf

https://projects.raspberrypi.org/en/projects/physical-computing/14
https://www.hackster.io/officine/interfacing-arduino-mkr-or-esp-via-mqtt-node-red-101-4833bc
https://grafana.com/blog/2023/10/23/monitor-temperature-and-humidity-with-grafana-and-raspberry-pi/
https://www.makerhero.com/blog/sensor-dht11-com-node-red-e-raspberry-pi/
https://blog.voltaicsystems.com/solar-powered-lora-radio-barometric-pressure-and-altimeter-tutorial/
https://timchooblog.wordpress.com/2016/06/14/configuring-the-johnny-five-robotics-library-to-work-in-node-red/
https://iotdesignpro.com/projects/interface-arduino-with-node-red-to-send-sensor-data-on-webpage

