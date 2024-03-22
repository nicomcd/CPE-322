*I pledge my Honor that I have abided by the Stevens Honor System*

> Study the GitHub repository Lesson 3 labs
> Install required Python packages such as jdcal, astral, and geopy

![Installing required Python packages](https://github.com/nicomcd/Engineering-Design-VI/blob/main/Images/Lab3installgeopy.png)

```
$ cd ~/iot
$ cd lesson3
$ python3 julian.py
Calendar Date: 2024-03-22
Julian Date: 2460391.5
Modified Julian Date: 60391.0

$ python3 date_example.py
Date: 2024-03-22
Date: 03-22-24
Day of Week: Friday
Month: March
Year: 2024
65 days after the first day of classes
41 days before the last day of classes

$ python3 datetime_example.py
2024-03-22 14:42:32.169097
2024-03-22 14:42:32.169314
2024-03-22 18:42:32.169365
1711132952.1693819
Fri Mar 22 14:42:32 2024
2024-03-22 14:42:32.169694
2024-03-22 18:42:32.169812

$ python3 time_example.py
Fri Mar 22 14:42:52 2024
```

When attempting to run `python3 sun.py 'New York'`, received error describing no module named 'pytz', so I installed it it using `pip install pytz`:
![Installing pytz](https://github.com/nicomcd/Engineering-Design-VI/blob/main/Images/Lab3pytz.png)

```
$ python3 sun.py "New York"
Information for New York/USA

Timezone: US/Eastern
Latitude: 40.72; Longitude: -74.00

Dawn:    2024-03-22 06:27:32.236849-04:00
Sunrise: 2024-03-22 06:55:22.556691-04:00
Noon:    2024-03-22 13:02:50-04:00
Sunset:  2024-03-22 19:10:34.618341-04:00
Dusk:    2024-03-22 19:38:28.724513-04:00


$ python3 moon.py
2024-03-22 Moon Phase: 11
2024-03-23 Moon Phase: 12
2024-03-24 Moon Phase: 13
2024-03-25 Moon Phase: 14
2024-03-26 Moon Phase: 15
2024-03-27 Moon Phase: 15
2024-03-28 Moon Phase: 16
2024-03-29 Moon Phase: 17
2024-03-30 Moon Phase: 18
2024-03-31 Moon Phase: 19
2024-04-01 Moon Phase: 20
2024-04-02 Moon Phase: 21
2024-04-03 Moon Phase: 22
2024-04-04 Moon Phase: 23
2024-04-05 Moon Phase: 24
2024-04-06 Moon Phase: 25
2024-04-07 Moon Phase: 26
2024-04-08 Moon Phase: 27
2024-04-09 Moon Phase: 0
2024-04-10 Moon Phase: 1
2024-04-11 Moon Phase: 2
2024-04-12 Moon Phase: 3
2024-04-13 Moon Phase: 4
2024-04-14 Moon Phase: 5
2024-04-15 Moon Phase: 6
2024-04-16 Moon Phase: 7
2024-04-17 Moon Phase: 8
2024-04-18 Moon Phase: 9
2024-04-19 Moon Phase: 10
2024-04-20 Moon Phase: 11

$ python3 coordinates.py "Samuel C. Williams Library"
Samuel C. Williams Library, Field House Road, Hoboken, Hudson County, New Jersey, 07030, United States
(40.74480675, -74.02532861159351)

$ python3 address.py "40.74480675, -74.02532861159351"
Samuel C. Williams Library, Field House Road, Hoboken, Hudson County, New Jersey, 07030, United States
(40.74480675, -74.02532861159351)
```

When attempting to run `python3 cpu.py`, received error describing no module named 'psutil', so I installed it it using `pip install psutil`:
![Installing psutil](https://github.com/nicomcd/Engineering-Design-VI/blob/main/Images/Lab3psutil.png)


```
$ python3 cpu.py
The number of physical cores =  4
The number of logical CPUs =  8
The utilization per second as a percentage for each CPU
[0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
[0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
[0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
[0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, 0.0]
[0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
[0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
[0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
[0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
[0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, 0.0]
[0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]

$ python3 battery.py
sbattery(percent=74.04, secsleft=<BatteryTime.POWER_TIME_UNKNOWN: -1>, power_plugged=False)

$ python3 documentstats.py document.txt
Word Count: 1343
Top Ten Words: [('our', 26), ('their', 20), ('has', 20), ('he', 19), ('them', 15), ('these', 13), ('have', 11), ('we', 11), ('us', 11), ('people', 10)]

```
