# File-Transfert

> English

This code has been created to send a file between two PC on the local net

**1) Installation**

To install this code, use this command :
````
git clone https://github.com/MathKode/File-Transfert.git
`````
If it's doesn't work, verify your permissions :
`````
sudo git clone https://github.com/MathKode/File-Transfert.git
``````
**2) What's contained in the directory**

After the installation, you have a new directory which is created. He contains the two main file :

- mainV2.py
- main_GUI.py

mainV2.py is a terminal version of the code where as main_GUI.py is the graphical version of the code

**3) mainV2.py**

This code was created with parser, this means that you have to put arguments. To see all of them, do :
`````
python3 mainV2.py -h
``````
Or
`````
python3 mainV2.py --help
```````

**The oblygatory Arguments**

The first is the *-r* or *-role*. He is served to defined the role of the machine which execute the code. The two role are :

- s (to server)
- c (to client)

The SERVER machine is the machine which receives the data and the CLIENT is the one which sends the file.


