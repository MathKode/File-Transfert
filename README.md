*INFO : Ce readme est écrit en Anglais et en français. This readme is written in english and in french*

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

**Example**

If I want to receive a file and that my ip is 192.168.1.27 :
``````
python3 mainV2.py -r s -i 192.168.1.27
````````
If I want to send the file xmas.png at the PC 192.168.1.27 :
``````
python3 mainV2.py -r c -i 192.168.1.27 -f xmas.png
``````
_____________________________________________________________
If I want to do a connection on a personal port (1234) instead of 5746 :
> Sever
``````
python3 mainV2.py -r s -i 192.168.1.27 -p 1234
````````
> Client
``````
python3 mainV2.py -r c -i 192.168.1.27 -p 1234 -f xmas.png
``````
_____________________________________________________________
If I want to send the file 1 by 1 byte instead of 8500 by 8500 :
> Sever (Same)
``````
python3 mainV2.py -r s -i 192.168.1.27
````````
> Client (Change)
``````
python3 mainV2.py -r c -i 192.168.1.27 -b 1 -f xmas.png
``````

**4) Issues**

1) *ZeroDivisionError: division by zero*

If you have this error, it's because the file what you want to send is so little. To resolve this, you have to change the value byte send.
So, reduce *-b* value until this works :
Try, on the client :
``````
python3 mainV2.py -r c -i 192.168.1.27 -b 500 -f xmas.png
``````
If it's still doesn't work, do :
``````
python3 mainV2.py -r c -i 192.168.1.27 -b 1 -f xmas.png
``````
**5) GUI interfaces**

A interface was made to this code :

<img src="/Img/interface.png" width="320" />

This work exactly as the console program.

***WARNING : click on the start button of the server (PC which receive) before the start button of the client***

> Français

Ce code a été crée pour échanger des fichiers entre deux PC qui sont connectés sur le même réseau local

**1) Installation**

Pour installer ce code, utiliser cette commande :
````
git clone https://github.com/MathKode/File-Transfert.git
`````
Si ça ne fonctionne pas, vérifier les permissions avec :
`````
sudo git clone https://github.com/MathKode/File-Transfert.git
``````
**2) Que contient le dossiers téléchargé**

Après l'installation, tu as un nouveau dossier qui a été crée. Il contient deux fichiers importants :

- mainV2.py
- main_GUI.py

mainV2.py est la version console/terminal du code alors que main_GUI.py est la version graphique :-)

**3) mainV2.py**

Ce code a été crée avec parser, cela signifie que tu vas devoir utiliser des arguments. Pour les voirs tous, fait :
`````
python3 mainV2.py -h
``````
Ou
`````
python3 mainV2.py --help
```````

**Les arguments obligatoires**

Le **premier** est le *-r* ou *-role*. Il est utilisé pour définir le role de la machine qui éxecute le code. Les deux roles sont :

- s (pour serveur)
- c (pour client)

La SERVEUR machine est la machine qui reçois le fichiers et le CLIENT est celle qui envoie le fichier.

Le **deuxième** est le *-i* ou *--ip*. Il est utilisé pour définir l'addresse ip du PC qui reçois les datas. Pour trouver son addresse ip, il faut faire :

> Sur windows
`````
ipconfig
``````
Le résultat est :
![](/Img/Ipconfig.png)
> Sur MacOs ou linux
`````
ifconfig
``````
Le résultat est :
![](/Img/Ifconfig.png)

Enfin, le **troisième** est le *-f* ou *--file* (SEULEUMENT POUR LE CLIENT). Cet argument est utilisé pour définier le fichier qui sera envoyé. 

**RECAP**

La machine qui reçoit le fichier (serveur) doit être configuré avec :
`````
python3 mainV2.py -r s -i IP_SERVEUR
``````
Et la machine qui envoie le fichier (client) :
``````
python3 mainV2.py -r c -i IP_SERVEUR -f NOM_DU_FICHIER
````````
***ATTENTION : La fichier doit être dans le dossier local (où le code est éxecuté)***

___________________________________________________________________________________________

**Arguments optionnels**

Le **quatrième** argument que nous pouvons rencontrer est *-p*  *--port*. Il est utiliser pour définir le port utiliser par le socket pour une connection. Par défaut, c'est 5746.

Le **cinquième** est *-b* ou *--byte*. Il est utilisé pour définir le nombre de "bit" envoyer par un socket (plus il est haut, plus se sera rapide mais il y a des risques d'erreurs)

**Exemples**

Si tu veux recevoir un fichier et que ton ip c'est :
``````
python3 mainV2.py -r s -i 192.168.1.27
````````
Si tu veux envoyer le fichier xmas.png au PC 192.168.1.27 :
``````
python3 mainV2.py -r c -i 192.168.1.27 -f xmas.png
``````
_____________________________________________________________
Si je veux personnaliser ma connection et changer de port (1234 au lieu 5746) :
> Seveur
``````
python3 mainV2.py -r s -i 192.168.1.27 -p 1234
````````
> Client
``````
python3 mainV2.py -r c -i 192.168.1.27 -p 1234 -f xmas.png
``````
_____________________________________________________________
Si je veux envoyer un fichier 1 byte par 1 byte au lieu de 8500 par 8500 (plus lent) :
> Seveur (Parreil)
``````
python3 mainV2.py -r s -i 192.168.1.27
````````
> Client (Change)
``````
python3 mainV2.py -r c -i 192.168.1.27 -b 1 -f xmas.png
``````

**4) Problèmes**

1) *ZeroDivisionError: division by zero*

Si tu as cette erreur, c'est que le fichier que tu veux envoyer est trop petit. Pour résoudre ce problème tu dois réduire la valeur byte send.
Pour la réduire utilise *-b*

Essaye donc ceci sur le client :
``````
python3 mainV2.py -r c -i 192.168.1.27 -b 500 -f xmas.png
``````
Si ça ne fonctionne toujours pas :
``````
python3 mainV2.py -r c -i 192.168.1.27 -b 1 -f xmas.png
``````
**5) GUI interfaces**

Une interface a été codé pour ce code :

<img src="/Img/interface.png" width="320" />

Cela marche exactement comme avec la console.

***ATTENTION : il faut cliquer sur le button start du serveur AVANT celui du client***
