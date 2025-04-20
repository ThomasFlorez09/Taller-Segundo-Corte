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