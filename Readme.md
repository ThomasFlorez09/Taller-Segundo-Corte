# **Taller Segundo Corte - IoT**
Este repositorio contiene el desarrollo del taller correspondiente al segundo corte de la asignatura de Internet de las Cosas (IoT). En este taller se exploran conceptos y herramientas fundamentales para la simulación y control de sistemas robóticos, así como la utilización de contenedores Docker para la implementación de entornos de trabajo portables y reproducibles. El taller se divide en tres puntos principales que abarcan investigación, simulación y despliegue de robots móviles y manipuladores y su desarrollo detallado se explica mediante un documento de Overleaf.

## Punto 1: Investigación y Simulación básica

El primer punto consiste en una investigación detallada sobre herramientas como ROS, MoveIt, Gazebo, LIDAR y SLAM, analizando su funcionamiento, aplicaciones y su integración en proyectos relacionados con IoT. Como parte del desarrollo práctico, se realizan dos ejemplos sencillos: uno de un robot móvil que se desplaza en un entorno simulado utilizando ROS, MoveIt y Gazebo, y otro de un robot equipado con sistema LIDAR y SLAM para la generación de mapas en tiempo real. Toda la información recopilada y el paso a paso de los ejemplos se documentaron en un archivo de Overleaf. Además, los códigos y configuraciones utilizadas se encuentran ubicados en este repositorio de GitHub.

## Punto 2: Simulación de Brazo Robótico UR5 con PyBullet

El punto 2 del taller corresponde a la simulación de un brazo robótico UR5 utilizando la librería PyBullet. Para ello, es necesario clonar los repositorios proporcionados por el docente, instalar las dependencias requeridas como pybullet y numpy, y ejecutar los scripts para verificar el correcto funcionamiento de la simulación inicialmente en Visual Studio Code. Posteriormente, se debe construir un Dockerfile que contenga el entorno de ejecución, creando una imagen Docker que permita desplegar la simulación de manera portable. Además el procedimiento y paso a paso se detalla en el documento de Overleaf.

## Punto 3: Simulación de Robot TurtleBot3 con LIDAR y SLAM en Docker

En el punto 3, se desarrolla la simulación de un robot TurtleBot3 que utiliza un sistema LIDAR y algoritmos de SLAM (gmapping) dentro de un contenedor Docker. Para ello, se debe preparar el entorno instalando ROS y los paquetes necesarios para la simulación y navegación autónoma. Se debe crear un Dockerfile que permita levantar el sistema de navegación y la visualización de mapas mediante RViz. Dentro del contenedor, se deben realizar pruebas de mapeo y desplazamiento. Además el procedimiento y paso a paso se detalla en el documento de Overleaf.

Para el desarrollo de este taller, se requiere contar con herramientas como Docker, Python 3.x, ROS (Robot Operating System), PyBullet, Git y Overleaf. Estas herramientas permiten la creación de entornos virtuales robustos y garantizan la portabilidad de las aplicaciones desarrolladas.

La estructura del repositorio está organizada de la siguiente manera: una carpeta punto1/ que contiene los ejemplos y la documentación en LaTeX; una carpeta punto2/ que incluye la simulación del brazo UR5 y su respectivo Dockerfile; y una carpeta punto3/ donde se encuentra la implementación de TurtleBot3 con LIDAR y SLAM, también con su Dockerfile.

Este trabajo fue desarrollado bajo la orientación del docente, en el marco de la asignatura de Internet de las Cosas (IoT). El objetivo principal es fortalecer las competencias de integración de tecnologías emergentes en entornos virtuales y simulados, en correspondencia con las tendencias actuales del IoT y la robótica moderna.

![image](https://github.com/ThomasFlorez09/Taller-Segundo-Corte/blob/main/images/Imagen1.png)


![image](https://github.com/ThomasFlorez09/Taller-Segundo-Corte/blob/main/images/Imagen25.png)
