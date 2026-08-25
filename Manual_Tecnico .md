# MANUAL TÉCNICO
## Instalación de Ubuntu, comandos de Linux y servidor Apache2

**Universidad:** Universidad de San Carlos de Guatemala  
**Facultad:** Facultad de Ingeniería  
**Escuela:** Escuela de Ciencias y Sistemas  
**Curso:** Prácticas Iniciales  
**Reporte:** Reporte 3  
**Nombre:** Cristian Adrián Fuentes Contreras  
**Carné:** 202308234 
**Fecha:** 27 de Agosto de 2026  

---

# 1. Introducción

En este manual se documenta el uso básico del sistema operativo Ubuntu mediante la terminal de comandos. Se presentan comandos para navegación, manejo de archivos, permisos, edición de texto y administración de paquetes.

También se documenta la instalación y configuración de un servidor web Apache2, realizando todo el procedimiento principal mediante comandos desde la terminal.

---

# 2. Instalación de Ubuntu

## 2.1 Modalidad utilizada

Para esta práctica se utilizó una instalación **virtualizada**, empleando **Oracle VirtualBox** como hipervisor.

El sistema operativo instalado fue **Ubuntu Desktop 26.04 LTS**, ejecutado dentro de una máquina virtual sobre Windows.

## 2.2 Proceso de instalación

De forma resumida, el procedimiento realizado fue:

1. Descargar la imagen ISO de Ubuntu.
2. Instalar Oracle VirtualBox.
3. Crear una nueva máquina virtual.
4. Asignar memoria RAM, procesadores y almacenamiento.
5. Seleccionar la imagen ISO de Ubuntu.
6. Iniciar la máquina virtual.
7. Seguir el asistente de instalación de Ubuntu.
8. Reiniciar la máquina virtual.
9. Comprobar que Ubuntu iniciara correctamente.

> [![Captura-de-pantalla-2026-08-13-162539.png](https://i.postimg.cc/d1xjmgth/Captura-de-pantalla-2026-08-13-162539.png)](https://postimg.cc/342G3SGh)

---

# 3. Comandos fundamentales de Linux

## 3.1 Comando `pwd`

### Propósito

El comando `pwd` muestra la ruta completa del directorio en el que se encuentra actualmente el usuario.

### Sintaxis

```bash
pwd
```

### Ejemplo

```bash
pwd
```

Resultado obtenido:

```text
/home/crismo
```

> [![Captura-de-pantalla-2026-08-24-175841.png](https://i.postimg.cc/3wDGQWKN/Captura-de-pantalla-2026-08-24-175841.png)](https://postimg.cc/zL8vnzHY)

---

## 3.2 Comando `cd`

### Propósito

El comando `cd` permite desplazarse entre directorios.

### Sintaxis

```bash
cd directorio
```

### Variaciones

```bash
cd ..
```

Regresa al directorio anterior.

```bash
cd ~
```

Regresa al directorio personal del usuario.

### Ejemplo práctico

```bash
cd ManualLinux
pwd
```

Resultado:

```text
/home/crismo/ManualLinux
```

> [![Captura-de-pantalla-2026-08-24-180105.png](https://i.postimg.cc/7Z5GSbJt/Captura-de-pantalla-2026-08-24-180105.png)](https://postimg.cc/4YTxgf5p)

---

## 3.3 Comando `ls`

### Propósito

El comando `ls` permite listar archivos y directorios.

### Sintaxis

```bash
ls
```

### Variaciones

```bash
ls -l
```

Muestra información detallada.

```bash
ls -a
```

Muestra también los archivos ocultos.

```bash
ls -la
```

Combina ambas opciones.

### Ejemplo

```bash
ls
ls -l
ls -a
```

> [![Captura-de-pantalla-2026-08-24-180214.png](https://i.postimg.cc/gJHnGZ1z/Captura-de-pantalla-2026-08-24-180214.png)](https://postimg.cc/Kk4ZNRZw)

---

# 4. Manejo de archivos y directorios

## 4.1 Comando `mkdir`

### Propósito

Permite crear directorios.

### Sintaxis

```bash
mkdir nombre_directorio
```

### Ejemplo

```bash
mkdir ManualLinux
```

### Directorios anidados

La opción `-p` permite crear varios niveles de directorios al mismo tiempo.

```bash
mkdir -p practica/documentos/copias
```

> [![Captura-de-pantalla-2026-08-24-180444.png](https://i.postimg.cc/NFPG07DR/Captura-de-pantalla-2026-08-24-180444.png)](https://postimg.cc/LgLFCPrs)

---

## 4.2 Comando `cp`

### Propósito

Permite copiar archivos o directorios.

### Sintaxis

```bash
cp origen destino
```

### Ejemplo práctico

```bash
cp archivo.txt copia.txt
```

Se creó una copia de `archivo.txt` llamada `copia.txt`.

### Variación

Para copiar directorios y su contenido se utiliza:

```bash
cp -r directorio directorio_copia
```

> [![Captura-de-pantalla-2026-08-24-180727.png](https://i.postimg.cc/zXs5PfP4/Captura-de-pantalla-2026-08-24-180727.png)](https://postimg.cc/6yfD8BKh)

---

## 4.3 Comando `mv`

### Propósito

Permite mover o renombrar archivos y directorios.

### Sintaxis

```bash
mv origen destino
```

### Ejemplo para renombrar

```bash
mv copia.txt archivo_nuevo.txt
```

### Ejemplo para mover

```bash
mv archivo_nuevo.txt practica/documentos/
```

El primer ejemplo cambia el nombre del archivo y el segundo permite trasladarlo hacia otro directorio.

> [![Captura-de-pantalla-2026-08-24-180850.png](https://i.postimg.cc/LX8MZgnq/Captura-de-pantalla-2026-08-24-180850.png)](https://postimg.cc/jWm1p56K)

---

## 4.4 Comando `rm`

### Propósito

Permite eliminar archivos.

### Sintaxis

```bash
rm archivo
```

### Ejemplo

```bash
rm archivo.txt
```

### Variaciones

Solicitar confirmación antes de eliminar:

```bash
rm -i archivo.txt
```

Eliminar un directorio y su contenido:

```bash
rm -r directorio
```

> [![Captura-de-pantalla-2026-08-24-181203.png](https://i.postimg.cc/hj5NzyFW/Captura-de-pantalla-2026-08-24-181203.png)](https://postimg.cc/dkG5g9t4)

---

## 4.5 Comando `rmdir`

### Propósito

Permite eliminar directorios que se encuentran vacíos.

### Sintaxis

```bash
rmdir directorio
```

### Ejemplo práctico

```bash
mkdir Temporal
rmdir Temporal
```

Posteriormente se utilizó `ls` para comprobar que el directorio había sido eliminado.

### Variación

```bash
rmdir -p carpeta/subcarpeta
```

Permite eliminar directorios anidados siempre que se encuentren vacíos.

> [![Captura-de-pantalla-2026-08-24-181315.png](https://i.postimg.cc/XNZY2tYg/Captura-de-pantalla-2026-08-24-181315.png)](https://postimg.cc/qgTrqbnt)

---

# 5. Superusuario y permisos

## 5.1 Comando `sudo`

### Propósito

`sudo` permite ejecutar temporalmente un comando con privilegios administrativos.

### Sintaxis

```bash
sudo comando
```

### Ejemplo práctico

```bash
sudo apt update
```

El sistema solicita la contraseña del usuario autorizado antes de ejecutar el comando.

> [![Captura-de-pantalla-2026-08-24-181758.png](https://i.postimg.cc/BnJsGz4m/Captura-de-pantalla-2026-08-24-181758.png)](https://postimg.cc/Xp1tfQZ5)

---

## 5.2 Comando `su`

### Propósito

El comando `su` permite cambiar de usuario desde la terminal.

### Sintaxis

```bash
su usuario
```

También puede utilizarse:

```bash
su -
```

para intentar iniciar una sesión como superusuario.

> En Ubuntu la cuenta `root` puede encontrarse deshabilitada de forma predeterminada, por lo que normalmente se utiliza `sudo` para realizar tareas administrativas.
[![Captura-de-pantalla-2026-08-24-193645.png](https://i.postimg.cc/6q0hDT9Q/Captura-de-pantalla-2026-08-24-193645.png)](https://postimg.cc/jnDNfxnV)

---

## 5.3 Comando `chmod`

### Propósito

Permite modificar los permisos de lectura, escritura y ejecución de archivos o directorios.

Los permisos principales son:

- `r`: lectura.
- `w`: escritura.
- `x`: ejecución.

### Sintaxis

```bash
chmod permisos archivo
```

### Ejemplo

```bash
chmod u+x archivo.sh
```

Este comando agrega permiso de ejecución al propietario del archivo.

También pueden utilizarse permisos numéricos:

```bash
chmod 755 archivo.sh
```
> [![Captura-de-pantalla-2026-08-24-184330.png](https://i.postimg.cc/T2ZgQVfG/Captura-de-pantalla-2026-08-24-184330.png)](https://postimg.cc/qgxNvCNZ)

---

## 5.4 Comando `chown`

### Propósito

Permite cambiar el propietario de un archivo o directorio.

### Sintaxis

```bash
sudo chown usuario archivo
```

### Ejemplo

```bash
sudo chown crismo archivo.txt
```

Para cambiar propietario y grupo:

```bash
sudo chown usuario:grupo archivo.txt
```

>[![Captura-de-pantalla-2026-08-24-184629.png](https://i.postimg.cc/7h7CjRwy/Captura-de-pantalla-2026-08-24-184629.png)](https://postimg.cc/BPSQKMjh)
---

# 6. Edición de archivos con Nano

`nano` es un editor de texto que funciona directamente desde la terminal.

### Sintaxis

```bash
nano archivo
```

Cuando se requiere modificar un archivo protegido se utiliza:

```bash
sudo nano archivo
```

### Comandos principales de Nano

| Acción | Teclas |
|---|---|
| Guardar | `Ctrl + O` |
| Confirmar nombre | `Enter` |
| Salir | `Ctrl + X` |
| Cancelar una acción | `Ctrl + C` |

Durante la práctica se utilizó Nano para modificar el archivo principal de Apache2.

> [![Captura-de-pantalla-2026-08-24-185238.png](https://i.postimg.cc/mkNLYWTS/Captura-de-pantalla-2026-08-24-185238.png)](https://postimg.cc/jn2YT9wW)

---

# 7. Gestión de paquetes con APT

APT es el administrador de paquetes utilizado en Ubuntu y otras distribuciones basadas en Debian.

## 7.1 Actualizar lista de paquetes

```bash
sudo apt update
```

Este comando consulta los repositorios configurados y actualiza la información sobre los paquetes disponibles.

> [![Captura-de-pantalla-2026-08-24-181758.png](https://i.postimg.cc/BnJsGz4m/Captura-de-pantalla-2026-08-24-181758.png)](https://postimg.cc/Xp1tfQZ5)

---

## 7.2 Actualizar paquetes instalados

```bash
sudo apt upgrade
```

Actualiza los paquetes instalados cuando existen versiones nuevas disponibles.

---

## 7.3 Instalar paquetes

### Sintaxis

```bash
sudo apt install paquete
```

### Ejemplo utilizado

```bash
sudo apt install apache2
```

Este comando instaló el servidor web Apache2.

> [![Captura-de-pantalla-2026-08-24-185706.png](https://i.postimg.cc/TPDXjv9L/Captura-de-pantalla-2026-08-24-185706.png)](https://postimg.cc/gwm5d51m)

---

## 7.4 Eliminar paquetes

Para eliminar un programa:

```bash
sudo apt remove paquete
```

>[![Captura-de-pantalla-2026-08-24-194708.png](https://i.postimg.cc/FzM9XFGG/Captura-de-pantalla-2026-08-24-194708.png)](https://postimg.cc/Wq7RMvBJ)

Para eliminar el programa junto con sus archivos principales de configuración:

```bash
sudo apt purge paquete
```

> [![Captura-de-pantalla-2026-08-24-194907.png](https://i.postimg.cc/2Sm11TFn/Captura-de-pantalla-2026-08-24-194907.png)](https://postimg.cc/CzPhtG2K)

> **Nota:** No se eliminó Apache2 porque es necesario para la actividad práctica del Reporte 3.

---

# 8. Instalación y configuración de Apache2

## 8.1 Actualización de repositorios

Antes de instalar Apache2 se actualizó el índice de paquetes utilizando:

```bash
sudo apt update
```

El comando finalizó correctamente y mostró los paquetes disponibles para actualización.

---

## 8.2 Instalación de Apache2

Se instaló el servidor HTTP Apache2 mediante:

```bash
sudo apt install apache2
```

Al finalizar la instalación se habilitaron automáticamente los componentes principales del servidor.

---

## 8.3 Verificación del servicio

Para comprobar el estado del servidor se utilizó:

```bash
systemctl status apache2
```

El resultado mostró:

```text
Active: active (running)
```

Esto confirmó que el servicio Apache2 se encontraba ejecutándose correctamente.

> [![Captura-de-pantalla-2026-08-24-190454.png](https://i.postimg.cc/7ZzBmHp7/Captura-de-pantalla-2026-08-24-190454.png)](https://postimg.cc/mPbNrsZ2)

---

## 8.4 Ingreso a la página de Apache2

Se abrió Firefox dentro de Ubuntu y se ingresó a:

```text
http://localhost
```

Se mostró la página predeterminada:

```text
Apache2 Default Page
It works!
```

Esto confirmó que el servidor respondía correctamente mediante HTTP.

> [![Captura-de-pantalla-2026-08-24-190608.png](https://i.postimg.cc/JnpKGGkC/Captura-de-pantalla-2026-08-24-190608.png)](https://postimg.cc/WFJ0yp85)

---

## 8.5 Directorio web de Apache2

Los archivos principales del sitio se encuentran en:

```text
/var/www/html/
```

Se accedió utilizando:

```bash
cd /var/www/html/
```

Luego se verificó la ubicación y el contenido:

```bash
pwd
ls
```

Se encontró el archivo:

```text
index.html
```

> [![Captura-de-pantalla-2026-08-24-190806.png](https://i.postimg.cc/0Nc7Ch2F/Captura-de-pantalla-2026-08-24-190806.png)](https://postimg.cc/1gVgmCFr)

---

## 8.6 Respaldo del archivo original

Antes de modificar la página se conservó una copia del archivo original renombrándolo:

```bash
sudo mv index.html index_original.html
```

Se verificó con:

```bash
ls
```

obteniendo:

```text
index_original.html
```

---

## 8.7 Creación de la nueva página

Se creó un nuevo archivo `index.html` utilizando Nano:

```bash
sudo nano index.html
```

El contenido utilizado fue:

```html
<!DOCTYPE html>
<html lang="es">

<head>
    <meta charset="UTF-8">
    <title>Reporte 3 - Apache2</title>
</head>

<body>
    <h1>Reporte 3 - Apache2</h1>
    <p>Nombre: [NOMBRE COMPLETO]</p>
    <p>Carné: [CARNÉ]</p>
</body>

</html>
```

La etiqueta:

```html
<meta charset="UTF-8">
```

permite representar correctamente caracteres como tildes y la letra ñ.

> [![Captura-de-pantalla-2026-08-24-191117.png](https://i.postimg.cc/fWXjG2Hn/Captura-de-pantalla-2026-08-24-191117.png)](https://postimg.cc/6TWvR0JY)

---

## 8.8 Verificación desde terminal

Se comprobó el contenido guardado mediante:

```bash
cat index.html
```

La terminal mostró correctamente el contenido del archivo.

> [![Captura-de-pantalla-2026-08-24-191301.png](https://i.postimg.cc/YSZYVYYh/Captura-de-pantalla-2026-08-24-191301.png)](https://postimg.cc/Jy3sHyTL)

---

## 8.9 Resultado final

Finalmente se volvió a:

```text
http://localhost
```

y se recargó la página.

Apache2 mostró correctamente la nueva página con:

- Título del Reporte 3.
- Nombre completo.
- Carné.

Esto confirmó que el archivo `index.html` fue modificado correctamente y que Apache2 estaba sirviendo el nuevo contenido.

> [![Captura-de-pantalla-2026-08-24-191401.png](https://i.postimg.cc/pVDzG9TQ/Captura-de-pantalla-2026-08-24-191401.png)](https://postimg.cc/vDZ4DZ5D)

---

# 9. Conclusiones

La práctica permitió familiarizarse con el uso de Ubuntu mediante la interfaz de línea de comandos. Se utilizaron comandos para navegación, creación, copia, modificación, movimiento y eliminación de archivos y directorios.

También se comprendió el funcionamiento básico del administrador de paquetes APT y el uso de privilegios administrativos mediante `sudo`.

Finalmente, se instaló y configuró correctamente Apache2, comprobando su funcionamiento mediante `localhost` y modificando su archivo `index.html` desde la terminal.

Con esta práctica se adquirieron conocimientos básicos necesarios para la administración de sistemas Linux y el despliegue de servicios web.