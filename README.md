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

The **first** is the *-r* or *-role*. He is used to define the role of the machine which execute the code. The two role are :

- s (to server)
- c (to client)

The SERVER machine is the machine which receives the data and the CLIENT is the one which sends the file.

The **second** is the *-i* or *--ip**. He is used to define the ip address of the server machine. To find the ip address of the machine which execute the code of server, do this :

> On windows
`````
ipconfig
``````
The result is :
![](/Img/Ipconfig.png)
> On MacOs or linux
`````
ifconfig
``````
The result is :
![](/Img/Ifconfig.png)

At last, the **third** is the *-f* or *--file* (ONLY TO THE CLIENT). This argument is used to define the file which is going to send.

**RECAP**

The machine who receive the file (server) have to be configure with :
`````
python3 mainV2.py -r s -i IP_SERVER
``````
And the machine who send the file (client) :
``````
python3 mainV2.py -r c -i IP_SERVER -f NAME_DU_FICHIER
````````
***WARNING : The file have to be in the local folder (in the directory where the code is stock)***

___________________________________________________________________________________________

**The Optional Argument**

The **fourth** argument that we can meet is *-p* or *--port*. He is used to define the port of socket the connection. By default, it's on 5746.

The **fifth** is *-b* or *--byte*. He is use to define the number of byte what we send in one socket (so he is high, so it's quick but the risk of error is taller)
