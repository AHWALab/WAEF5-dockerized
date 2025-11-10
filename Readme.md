# Modelo Hidrológico EF5 Dockerizado para Cuba (Resolución de 1 km).

Taller EF5 - Cuba.
Este repositorio contiene todos los materiales necesarios para ejecutar el modelo hidrológico EF5 para Cuba a una resolución de 1 km.

## Requisitos del sistema

- Una computadora portátil con **al menos 8 GB de RAM**.
- Una cuenta de Google para acceder a Google Colab.

---

## Instrucciones de configuración

### 1. Instalar Docker Desktop

1. Descarga Docker Desktop (~600 MB) desde el sitio oficial:  
   [Descarga de Docker Desktop](https://www.docker.com/products/docker-desktop/)

2. Usa el botón **Download Docker Desktop** (no se necesita cuenta).

3. Después de la instalación, ajusta la configuración de recursos de Docker para asignar al menos 8 GB de RAM:
   - Abre Docker Desktop.
   - Ve a **Settings** > **Resources** > **Advanced**.
   - Ajusta el control de **Memory** a **8 GB**.
   - Haz clic en **Apply & Restart**.

---

### 2. Descargar o Clonar Este Repositorio

Puedes descargar o clonar el repositorio en tu máquina.

#### Opción 1: Descargar

Haz clic en el botón azul **Code** en este repositorio.
Selecciona **Download ZIP** y extrae el contenido.
Asegúrate de que la carpeta extraída esté en una ubicación sin espacios en su ruta (por ejemplo, `model_repository`).

#### Opción 2: Clonar la rama

Copia la URL del repositorio en **Code > HTTPS**.
Ejecuta el siguiente comando en tu terminal:

```bash
git clone --branch CUEF5-dockerized --single-branch https://github.com/AHWALab/WAEF5-dockerized.git
```

Coloca la carpeta clonada en un directorio sin espacios en su nombre.

**Importante:** Evita nombres de carpetas con espacios, ya que pueden causar errores al ejecutar el modelo.

---

### 3. Construir el contenedor Docker de EF5

#### **macOS/Linux**

1. Abre tu terminal y navega a la carpeta principal del proyecto.  
   Ejemplo para una carpeta en tu Escritorio:
   ```bash
   cd ~/Desktop/EF5CU-dockerized-main/
   ```
2. Entra a la carpeta `docker/`:
   ```bash
   cd docker
   ```
3. Ejecuta el script de construcción:
   ```bash
   bash build_ef5_container.sh
   ```
4. Sigue las instrucciones en la terminal. Cuando el proceso termine, verifica que la imagen del contenedor EF5 se haya construido revisando el panel **Images** en Docker Desktop.

#### **Windows**

1. Abre el Explorador de archivos y navega a la carpeta principal del proyecto.
2. Entra a la carpeta `docker/`.
3. Haz doble clic en el archivo `build_ef5_container.bat`.
4. Se abrirá una ventana de comandos que mostrará el proceso de construcción. Al finalizar, verifica en el panel **Images** de Docker Desktop que la imagen se haya creado.

---

### Verificar la construcción

Después de una construcción exitosa, puedes verificar la presencia del contenedor EF5 en Docker Desktop:

1. Abre Docker Desktop.
2. Ve a la pestaña **Images**.
3. Busca una imagen llamada `ef5-container`.

---

La imagen de Docker de EF5 ya está lista para ejecutarse para el taller.

---
