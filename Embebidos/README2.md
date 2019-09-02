# Instalación del driver USBASP

Guía básica para la instalación del driver USBASP para Windows 10 o similares.


- ### Paso 1

Conectar el USBASP en el puerto USB. Ingresar a ***"Administrador de dispositivos"*** y dirigirse a ***Atmel USB Devices***. Verificar que el dispositivo USBasp no se encuentre con el signo de admiración amarillo. Si este es el caso, el driver se encuentra instalado; de lo contrario, realizar los siguientes pasos.

<img style="width: 40%;" src="./images/d-i01.JPG" />

- ### Paso 2

Descargar el comprimido ***"Windows USBasp Drivers"*** haciendo click [aquí](https://github.com/electronica-utec/comunidad/raw/master/Embebidos/resources/Windows%20USBasp%20Drivers.zip). Descomprimir en la carpeta de su elección.

- ### Paso 3

Presionar la tecla ***Shift*** y reiniciar su computadora sin dejar de presionar la tecla. Al reiniciar el sistema aparecerá la siguiente ventana de opciones. Seleccionar ***Solucionar Problemas***.

<img style="width: 55%;" src="./images/d-i02.JPG" />

Elegir la opción ***Restablecer tu PC***.

<img style="width: 55%;" src="./images/d-i03.JPG" />

Ingresar a ***Configuración de inicio***.

<img style="width: 55%;" src="./images/d-i04.JPG" />

Presionar el botón de ***Reiniciar***.

<img style="width: 55%;" src="./images/d-i05.JPG" />

Elegir la opción ***7) Deshabilitar el uso obligatorio de controladores firmados*** presionando la tecla 7.

<img style="width: 55%;" src="./images/d-i06.JPG" />

El equipo se reiniciará. 

- ### Paso 4

Hacer clik derecho en USBasp e ingresar a ***Actualizar software de controlador ...***.

<img style="width: 55%;" src="./images/d-i07.JPG" />

Elegir la opción ***Buscar software de controlador en el equipo***.

<img style="width: 65%;" src="./images/d-i08.JPG" />

Finalmente, elegir la carpeta libusb_1.2.4.0 descargado en el paso 2. Aceptar e ignorar si aparece un mensaje de advertencia.

<img style="width: 65%;" src="./images/d-i09.JPG" />

Si todo está instalado correctamente, aparecerá el siguiente mensaje.

<img style="width: 55%;" src="./images/d-i10.JPG" />


## Autores

* [**Jhonatan Macazana**](https://github.com/jhonatanmacazana) - *Driver USBASP*



## Reconocimientos

* Gustavo Solano y Franco Lama por el contenido y la estructura de la documentación.