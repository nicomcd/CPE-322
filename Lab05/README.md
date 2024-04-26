*I pledge my Honor that I have abided by the Stevens Honor System*

- Study the GitHub repository Lesson 5 labs
- Install Paho-MQTT
- Change directory to the iot repository
- Update the repository with git pull
- Change directory to Lesson 5
- Run python3 subcpu.py on one Terminal
- Run python3 pubcpu.py on another


### Lab 5A: Eclipse Mosquitto and Eclipse Paho


```
$ pip install paho-mqtt
$ git pull
$ cd iot/lesson5
```

In one terminal:

```
$ python3 subcpu.py

/home/nicoxmcd/iot/lesson5/subcpu.py:8: DeprecationWarning: Callback API version 1 is deprecated, update to latest version
  client = mqtt.Client(mqtt.CallbackAPIVersion.VERSION1)
Connected with result code 0
MyCPU 2024-04-26 00:53:18
MyCPU CPU Usage:   0.0 %
MyCPU 2024-04-26 00:53:28
MyCPU CPU Usage:   0.0 %
MyCPU 2024-04-26 00:53:38
MyCPU CPU Usage:   0.0 %
MyCPU 2024-04-26 00:53:48
MyCPU CPU Usage:   0.0 %
MyCPU 2024-04-26 00:53:58
MyCPU CPU Usage:   0.0 %
MyCPU 2024-04-26 00:54:08
MyCPU CPU Usage:   0.0 %
MyCPU 2024-04-26 00:54:18
MyCPU CPU Usage:   0.0 %
```


In another terminal: 

```
$ cd iot/lesson5
$ python3 pubcpu.py

/home/nicoxmcd/iot/lesson5/pubcpu.py:6: DeprecationWarning: Callback API version 1 is deprecated, update to latest version
  mqttc = mqtt.Client(mqtt.CallbackAPIVersion.VERSION1)
2024-04-26 00:53:18
CPU Usage:   0.0 %
2024-04-26 00:53:28
CPU Usage:   0.0 %
2024-04-26 00:53:38
CPU Usage:   0.0 %
2024-04-26 00:53:48
CPU Usage:   0.0 %
2024-04-26 00:53:58
CPU Usage:   0.0 %
2024-04-26 00:54:08
CPU Usage:   0.0 %
2024-04-26 00:54:18
CPU Usage:   0.0 %
2024-04-26 00:54:28
CPU Usage:   0.0 %
2024-04-26 00:54:38
CPU Usage:   0.0 %
2024-04-26 00:54:48
CPU Usage:   0.0 %
```

![Subscribe](https://github.com/nicomcd/Engineering-Design-VI/assets/35404943/2af7de64-1e9b-4b8a-97df-d5d3030c450f)
