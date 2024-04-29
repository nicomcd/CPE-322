*I pledge my Honor that I have abided by the Stevens Honor System*

- Study the GitHub repository Lesson 8
- Install Python packages
- Save the Lab 7 Google sheet in CSV format to ~/demo
- Copy ~/iot/lesson8/plt_final.py and plt_cv2.py to ~/demo
- Edit plt_final.py and plt_cv2.py to read the CSV file with customized plot titles
- Run plt_final.py and plt_cv2.py


The following code block contains the commands from the lab assignment and its respective output:

### Lab 8A: Examples

**Setup**
```
$ sudo pip3 install numpy scipy scikit-learn matplotlib pandas tensorflow keras
$ sudo apt update
$ sudo apt install python3-scipy
$ sudo apt install python3-matplotlib
$ sudo apt install python3-pandas
$ sudo apt install libopenblas-dev
$ sudo apt install libatlas-base-dev
$ sudo pip3 install -U numpy
$ sudo pip3 install --only-binary :all: -U scikit-learn
$ sudo pip3 install -U tensorflow
$ sudo pip3 install -U keras==2.3.1
```
**Python Examples**
```
$ python3
>>> import numpy as np
>>> a = np.arange(6)
>>> a
array([0, 1, 2, 3, 4, 5])
>>> b = np.arange(12).reshape(4, 3)
>>> b
array([[ 0,  1,  2],
       [ 3,  4,  5],
       [ 6,  7,  8],
       [ 9, 10, 11]])
>>> c = np.arange(24).reshape(2, 3, 4)
>>> c
array([[[ 0,  1,  2,  3],
        [ 4,  5,  6,  7],
        [ 8,  9, 10, 11]],

       [[12, 13, 14, 15],
        [16, 17, 18, 19],
        [20, 21, 22, 23]]])
>>> b.shape
(4, 3)
>>> b.reshape(-1)
array([ 0,  1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11])
>>> b.reshape(-1, 1)
array([[ 0],
       [ 1],
       [ 2],
       [ 3],
       [ 4],
       [ 5],
       [ 6],
       [ 7],
       [ 8],
       [ 9],
       [10],
       [11]])
>>> b.reshape(2, -1)
array([[ 0,  1,  2,  3,  4,  5],
       [ 6,  7,  8,  9, 10, 11]])
>>> d = np.array([20, 30, 40, 50])
>>> e = np.arange(4)
>>> f = d-e
>>> f
array([20, 29, 38, 47])
>>> e**2
array([0, 1, 4, 9])
>>> A = np.array([[1, 1], [0, 1]])
>>> B = np.array([[2, 0], [3, 4]])
>>> A*B
array([[2, 0],
       [0, 4]])
>>> A.dot(B)
array([[5, 4],
       [3, 4]])
>>> np.dot(A, B)
array([[5, 4],
       [3, 4]])
>>> g = np.ones((2, 3), dtype=int)
>>> g
array([[1, 1, 1],
       [1, 1, 1]])
>>> h = np.random.random((2, 3))
>>> h
array([[0.69795395, 0.17029243, 0.41008948],
       [0.21018261, 0.97756872, 0.1405194 ]])
>>> g *= 3
>>> g
array([[3, 3, 3],
       [3, 3, 3]])
>>> h += g
>>> h
array([[3.69795395, 3.17029243, 3.41008948],
       [3.21018261, 3.97756872, 3.1405194 ]])
>>> k = np.random.random((2, 3))
>>> k
array([[0.13640929, 0.48341917, 0.86785151],
       [0.02981515, 0.27800848, 0.96750918]])
>>> k.sum()
2.7630127818688806
>>> k.min()
0.029815152511911025
>>> k.max()
0.9675091802725065
>>> m = np.arange(12).reshape(3, 4)
>>> m
array([[ 0,  1,  2,  3],
       [ 4,  5,  6,  7],
       [ 8,  9, 10, 11]])
>>> m.sum(axis = 0)
array([12, 15, 18, 21])
>>> m.min(axis = 1)
array([0, 4, 8])
>>> m.cumsum(axis = 1)
array([[ 0,  1,  3,  6],
       [ 4,  9, 15, 22],
       [ 8, 17, 27, 38]])
>>> n = np.arange(5)
>>> n
array([0, 1, 2, 3, 4])
>>> n[[1, 3, 4]] = 0
>>> n
array([0, 0, 2, 0, 0])
>>> exit()
```
![Python Examples](https://github.com/nicomcd/Engineering-Design-VI/assets/35404943/8fe621aa-2f7a-418b-a4f7-ac2733337e91)
```
$ cd ~/iot/lesson8
$ python3 pyplot_simple.py
```
![image](https://github.com/nicomcd/Engineering-Design-VI/assets/35404943/43b3e124-d234-46e6-aab8-cc001c97fda8)
```
$ python3 simple_plot.py
```
![image](https://github.com/nicomcd/Engineering-Design-VI/assets/35404943/325224a3-6d08-49e0-b276-a2835e1c9988)

```
$ python3 pyplot_formatstr.py
```

```
$ python3 ticklabels_demo_rotation.py
```

```
$ python3 pyplot_three.py
```

```
$ python3 pyplot_two_subplots.py
```

```
$ python3 pyplot_scales.py
```

```
$ python3 pyplot_annotate.py
```

```
$ python3 major_minor_demo1.py
```

```
$ python3 legend_demo.py
```


### Lab 8B: Data Analysis
Save the Google Sheet with the cpudata created in Lab 7 as a .csv file to the ~/demo folder. I saved mine as cpudata.csv.
![csv](https://github.com/nicomcd/Engineering-Design-VI/assets/35404943/c14a7ed1-2413-4104-8510-aa979fd16788)
```
$ cd demo
$ cp ~/iot/lesson8/plt_cv2.py .
$ cp ~/iot/lesson8/plt_final.py .
```
Edit the files to read your .csv file.
```
$ nano plt_final.py
```
![plt_final](https://github.com/nicomcd/Engineering-Design-VI/assets/35404943/f5fe4372-0221-4c0f-a6f5-39b4a9df6625)

```
$ nano plt_cv2.py
```
![plt_cv2](https://github.com/nicomcd/Engineering-Design-VI/assets/35404943/4779602d-59df-42d4-8199-7c1e368b62d6)

![image](https://github.com/nicomcd/Engineering-Design-VI/assets/35404943/79a5b09b-f02b-4027-ba50-f3f187b52164)
