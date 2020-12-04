# MSD-Configuración
En esta sección se detalla la configuración e instalación de la tarjeta MSD utilizada en el robot guía
### 4-1 Grabado del software en la tarjeta micro SD

En primera instancia formateamos la memoria con SD Formater mediante el adaptador de memoria enchufado a un puerto USB de la PC:

![myimage-alt-tag](https://github.com/NorbertoAramayo/archivosnuevos/blob/main/Configuraci%C3%B3n%20de%20la%20MSD%202%20github.jpg)

Luego utilizamos USB Image Tool para grabar la imagen del sistema que utilizará el robot mediante el adaptador USB de memoria enchufado a un puerto USB de la PC :

![myimage-alt-tag](https://github.com/NorbertoAramayo/archivosnuevos/blob/main/USB%20Image%20Tool%20github.jpg)

### 4-2 Armado de la máquina virtual con Ubuntu 18.04 y Jupiter para  trabajar con el código que utilizará el robot.

Cabe destacar que tanto Jetson Nano como Blackberry utilizan el sistema operativo Linux por lo que es necesario contar con una máquina que utilice este SO.  Si bien hay diversas manera de obtener una máquina vbrtual entre las que podemos citar la utilización de software específico para realizar la virtualización como VMware, VirtualBox y otros, tambien se podría utilizar dual boot en la PC para seleccionar un arranque con Linux, en este caso uitlizaremos la posibilidad que nos brinda Windows 10 de ejecutar una terminal de Ubuntu como una aplicación.

Inicialmente debemos ener actualizado Windos 10 e instalar el Subsistema de Windows para Linux con:

dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart

Luego debemos habilitar la característica opcional Plataforma de máquina virtual en Windos ejecutando en el power Shell el comando:

dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart

para luego descargar el paquete de Linux, Ubuntu 18.04 LTS

Tendeemos de ese modo Ubuntu 18.04 en el escritorio de windows con un acceso que se verá de la siguiente manera

![myimage-alt-tag](https://github.com/NorbertoAramayo/archivosnuevos/blob/main/icono%20ubuntu.jpg)

Accedemos a Ubuntu 18.04 

![myimage-alt-tag](https://github.com/NorbertoAramayo/archivosnuevos/blob/main/ubuntu%2018.04.jpg)

### 4-3 Instaalción de Jupiter en Ubuntu 18.04:

Actualizamos el índice de paquetes local apt 

$ sudo apt update

Luego descargamos e instalaremos los paquetes
Instalamos pip y los archivos de encabezado de Python, utilizados por algunas dependencias de Jupyter:

sudo apt install python3-pip python3-dev

Creamos un entorno virtual de Python para administrar nuestros proyectos e instalaremos Jupyter en este entorno virtual.

$ sudo -H pip3 install --upgrade pip


$ sudo -H pip3 install virtualenv

Creamos un directorio en el que podamos guardar los archivos de nuestro proyecto e ingresamos en él

$ mkdir ~/miproyecto

$ cd ~/miproyecto

Creamos un entorno virtual de Python dentro del directorio miproyecto

Activamoe el entorno virtual para instalar Jupiter

$ source miproyecto_env/bin/activate

Instalamos jupyter

$ pip install jupyter

Finalmente ejecutamos jupyter

$ jupyter notebook

Nos saldrá una notificación como la siguiente, por lo que usamos estas direcciones para ejecutarla en un navegador

![myimage-alt-tag](https://github.com/NorbertoAramayo/archivosnuevos/blob/main/ejecutando%20jupyter.jpg)

Y se mostrará jupyter para poder trabajar con el código de nuestro vehículo guía experimental

![myimage-alt-tag](https://github.com/NorbertoAramayo/archivosnuevos/blob/main/jupyter.jpg)
## [Regresar](https://github.com/NorbertoAramayo/Vehiculo-Guia-Autonomo-Experimental/blob/main/README.md#4-software-utilizado-1)
