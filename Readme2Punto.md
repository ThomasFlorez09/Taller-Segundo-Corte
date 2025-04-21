# **Segundo Punto - Simulación de un brazo robótico (UR5) con PyBullet**
Para el desarrollo de la simulación correspondiente, inicialmente se realiza la simulación en Visual Studio Code y posteriormente se realizará la creación del contenedor para su ejecución empleando Docker. Para esto se tienen dos códigos proporcionados por el docente. El primer código es un archivo de Python que utiliza PyBullet, un motor de simulación física en tiempo real, para cargar y controlar un robot personalizado con dos articulaciones y emplea otras librerias como pybullet_data, time, numpy y os; mientras que el segundo código corresponde a la descripción del robot en formato URDF y se presenta la estructura y propiedades físicas de este.

## Código de Python
En el código, primero se realiza la comprobación de que el archivo URDF del robot está en la misma carpeta en la que se va a hacer la ejecución y se inicializa Pybullet conectando y habilitando a la simulación en modo gráfico (GUI) para visualizarla. 

![image](https://github.com/ThomasFlorez09/Taller-Segundo-Corte/blob/main/images/Imagen1.png)

Posteriormente, se realiza la configuración del entorno físico y visualización, en donde se establece la gravedad,se agrega el directorio de datos extra y se ajusta la posición inicial de la cámara en la escena para visualizar bien el robot. También se carga el plano base ("plane.urdf") y el robot definido en el archivo URDF "two_joint_robot_custom.urdf".

![image](https://github.com/ThomasFlorez09/Taller-Segundo-Corte/blob/main/images/Imagen2.png)

Después se agregan los controles interactivos para controlar las dos articulaciones, la velocidad el el botón de pausa. 

![image](https://github.com/ThomasFlorez09/Taller-Segundo-Corte/blob/main/images/Imagen3.png)

Finalmente, en un bucle while se leen los valores actuales de los deslizadores, se aplican esos valores como posiciones deseadas a los motores de las articulaciones y se ajusta la velocidad de simulación con base en el control de speed. También permite pausar o reanudar dinámicamente.

![image](https://github.com/ThomasFlorez09/Taller-Segundo-Corte/blob/main/images/Imagen4.png)

## Código URDF
El segundo código que corresponde al archivo URDF que es un formato utilizado para describir la estructura y propiedades físicas de un robot en ROS. El código define un robot llamado two_joint_robot con dos articulaciones (joints) y tres enlaces (links).

Inicialmente se modelada la base del robot como un cilindro con un radio de 0.2 metros y una longitud de 0.1 metros. Tiene un color azul y una masa de 1 kg. La inercia se define con los valores proporcionados para ixx, iyy, e izz.

![image](https://github.com/ThomasFlorez09/Taller-Segundo-Corte/blob/main/images/Imagen5.png)

Para el link1 es un enlace rectangular de tamaño 0.1x0.1x0.5 metros, que tiene una masa de 1 kg, está coloreado de rojo y está ubicado en la posición (0, 0, 0.25), lo que significa que se desplaza 0.25 metros en el eje Z respecto a su origen. El link 2 es la misma figura con las misma dimensiones pero de color verde.

![image](https://github.com/ThomasFlorez09/Taller-Segundo-Corte/blob/main/images/Imagen6.png)
![image](https://github.com/ThomasFlorez09/Taller-Segundo-Corte/blob/main/images/Imagen7.png)

El joint1 es una articulación rotatoria que conecta base_link con link1, la articulación rota alrededor del eje Z y los límites de movimiento van de -π a +π radianes (360 grados), y tiene un esfuerzo máximo de 100 unidades y una velocidad máxima de 5 unidades. Por otro lado, el joint2 es otra articulación rotatoria que conecta link1 con link2 y tiene las mismas características que la articulación anterior.

![image](https://github.com/ThomasFlorez09/Taller-Segundo-Corte/blob/main/images/Imagen8.png)
![image](https://github.com/ThomasFlorez09/Taller-Segundo-Corte/blob/main/images/Imagen9.png)

Finalmente, el end_effector es una esfera de radio 0.05 metros, representando el extremo del brazo del robot. Está coloreado de blanco y tiene una masa de 0.1 kg.

![image](https://github.com/ThomasFlorez09/Taller-Segundo-Corte/blob/main/images/Imagen10.png)

## Ejecución en Visual Studio Code

Para la ejecución del código .py en Visual Studio Code fue necesario crear un entorno virtual para la correcta instalación de las librerías y entorno gráfico necesario. En este caso el entrono virtual creado es llamado "venv" y se hace en la misma carpeta donde se tienen los dos códigos explicados anteriormente.

Para la creación del entorno se ejecuta la siguiente línea en el terminal.

![image](https://github.com/ThomasFlorez09/Taller-Segundo-Corte/blob/main/images/Imagen11.png)

Para la activación se ejecuta la siguiente línea de comando.

![image](https://github.com/ThomasFlorez09/Taller-Segundo-Corte/blob/main/images/Imagen12.png)

Posteriormente, se evidencia que ahora aparece (venv) antes del directorio en el terminal, indicando que ya nos encontramos en el entorno virtual. Después se realiza la instalción de las librería necesarias, en este caso, pybullet y numpy. Los comandos correspondientes se presentan a continuación.

![image](https://github.com/ThomasFlorez09/Taller-Segundo-Corte/blob/main/images/Imagen13.png)
![image](https://github.com/ThomasFlorez09/Taller-Segundo-Corte/blob/main/images/Imagen14.png)

Para ejecutar el código desde el terminal de Visual Code se puede utilizar el siguiente comando.

![image](https://github.com/ThomasFlorez09/Taller-Segundo-Corte/blob/main/images/Imagen15.png)

Inmediatamente se abre la interfaz grágica de pybullet en la que se evidencia el robot programado anteriomente con los slides correspondientes para su movimiento. Para finalizar la ejecución se puede presionar Ctrl + C.

![image](https://github.com/ThomasFlorez09/Taller-Segundo-Corte/blob/main/images/Imagen16.png)

## Creación del contenedor de Docker, montaje y ejecución del brazo robótico.
Para ejecutar el brazo robótico utilizando contenedores de docker, en el bash de Ubuntu se crea un nuevo directorio para el proyecto, el cual es llamado SegundoPunto el comando para crear la carpeta se presenta a continuación. 

![image](https://github.com/ThomasFlorez09/Taller-Segundo-Corte/blob/main/images/Imagen17.png)

En este mismo directorio es necesario tener el archivo main.py y two_joint_robot_custom.urdf para la correcta ejecución y se crea el archivo Dockerfile empleando el comando nano para su correspondiente edición.

![image](https://github.com/ThomasFlorez09/Taller-Segundo-Corte/blob/main/images/Imagen18.png)
![image](https://github.com/ThomasFlorez09/Taller-Segundo-Corte/blob/main/images/Imagen19.png)

En el Dockerfile se indica la imagen oficial de Python 3.10, versión "slim", que es más liviana. Después se actualizan e instalan las dependencias necesarias para la creación del contenedor.

- apt-get update: Actualiza el índice de paquetes disponibles en el contenedor.
- apt-get install -y \: Instala paquetes sin pedir confirmación interactiva.
- x11-apps: Para hacer pruebas de aplicaciones gráficas en X11.
- libgl1-mesa-glx: Biblioteca para renderizar gráficos OpenGL, usada por PyBullet.
- libglib2.0-0: Biblioteca de utilidades comunes usada por muchas apps gráficas.
- libsm6: Session Management para X11.
- libxext6: Extensiones adicionales para X11.
- libxrender1: Renderizado de gráficos vectoriales (necesario para GUI).

![image](https://github.com/ThomasFlorez09/Taller-Segundo-Corte/blob/main/images/Imagen20.png)

Posteriormente se establece el directorio de trabajo dentro del contenedor y se copian los archivos.

- COPY main.py: Copia el archivo main.py.
- COPY two_joint_robot_custom.urdf: Copia el archivo URDF.
- COPY --from=python:3.10-slim /usr/lib /usr/lib: Copia las bibliotecas del sistema desde la imagen base original.

![image](https://github.com/ThomasFlorez09/Taller-Segundo-Corte/blob/main/images/Imagen21.png)

Finalmente se instalan las dependencias de Python y se ejecuta el script. El archivo debe ser guardado.

![image](https://github.com/ThomasFlorez09/Taller-Segundo-Corte/blob/main/images/Imagen22.png)

Para la creación de la imagen del contenedor se utiliza la línea a continuación.

![image](https://github.com/ThomasFlorez09/Taller-Segundo-Corte/blob/main/images/Imagen23.png)

Después de que se crea correctamente, se debe permitir a Docker acceder al servidor X11.

![image](https://github.com/ThomasFlorez09/Taller-Segundo-Corte/blob/main/images/Imagen24.png)

Para la ejecución del contenedor se debe escribir en el bash las líneas que se presentan a continuación.

![image](https://github.com/ThomasFlorez09/Taller-Segundo-Corte/blob/main/images/Imagen25.png)

Al igual que en la ejecución anterior, se abre automáticamente la interfáz gráfica de Pybullet y la ejecución finaliza al presionar Ctrl + C.

![image](https://github.com/ThomasFlorez09/Taller-Segundo-Corte/blob/main/images/Imagen26.png)
