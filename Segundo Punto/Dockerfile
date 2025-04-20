FROM python:3.10-slim

# Instalar dependencias del sistema
RUN apt-get update && apt-get install -y \
    x11-apps \
    libgl1-mesa-glx \
    libglib2.0-0 \
    libsm6 \
    libxext6 \
    libxrender1 \
    && rm -rf /var/lib/apt/lists/*

# Crear y establecer el directorio de trabajo
WORKDIR /app

# Copiar los archivos necesarios
COPY main.py .
COPY two_joint_robot_custom.urdf .
COPY --from=python:3.10-slim /usr/lib /usr/lib

# Instalar dependencias de Python
RUN pip install --no-cache-dir pybullet numpy

# Comando para ejecutar el script
CMD ["python", "main.py"]
