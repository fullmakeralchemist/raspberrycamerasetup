# Configuración de Cámara Raspberry

Una de las aplicaciones más utilizadas en Raspberry es el uso de cámaras, para utilizar Tensorflow y darle la capacidad de detectar objetos. Ahora que la Raspberry Pi es lo suficientemente rápida para realizar el aprendizaje automático, agregar estas funciones en proyectos es más sencillo.
 
Esta guía le mostrará los pasos para aprender a conectar el módulo de cámara Raspberry Pi, tome fotografías, grabe videos y aplique efectos de imagen.
 
Es importante conocer bien el módulo de cámara antes de comenzar a crear nuestras aplicaciones.
 
Sin mas que decir comencemos.

## 1.Materiales

Existen múltiples opciones pero en esta guía te daré dos opciones para que elijas la que te agrade más, por parte de Raspberry Pi existen dos módulos de cámara hablaré de ellos más adelante.
 
*   Laptop
*   Raspberry Pi 4
*   Fuente de alimentación (De preferencia adquirir junto con tu Raspberry la fuente oficial para no tener ningún problema, si es que no tienes mucha experiencia [USB-C Power Supply](https://www.raspberrypi.org/products/type-c-power-supply/))
* Smartphone con función Mobile Hotspot
*  Tarjeta Micro SD 
*  [Raspberry Pi High Quality Camera](https://www.adafruit.com/product/4561) (es la que usare en esta guía, pero puedes utilizar la [Raspberry Pi Camera Board v2](https://www.adafruit.com/product/3099) es la versión anterior y mas económica.)
* [6mm 3MP Wide Angle Lens for Raspberry Pi HQ Camera - 3MP](https://www.adafruit.com/product/4563) (el modulo HQ camera, nos permite utilizar lentes, este elemento es opcional en caso de utilizar la segunda opción de cámara.
* [Flex Cable for Raspberry Pi Camera](https://www.adafruit.com/product/2087) (suele venir incluido en la compra de los módulos Raspberry Pi Camera).
* Trípode de cámara (**Nota: solo en caso de usar el módulo HQ.** la ventaja del módulo HQ es que cuenta con una montura para trípodes con standard 1/4”-20, que es con el que cuentan la mayoría  de los trípodes actuales, te dejo un link de una opción de compra en [Amazon](https://www.amazon.com.mx/Ubeesize-tel%C3%A9fono-ajustable-distancia-Universal/dp/B06Y2VP3C7/ref=sr_1_3?__mk_es_MX=%C3%85M%C3%85%C5%BD%C3%95%C3%91&dchild=1&keywords=%C2%BC%22-20+tripod&qid=1620010127&refinements=p_36%3A9841539011&rnid=9754432011&s=electronics&sr=1-3))
 
Opcional:
* [Raspberry Pi HQ Camera Case](https://learn.adafruit.com/raspberry-pi-hq-camera-case/3d-printing) (En caso de que cuentes con una impresora 3D o de hacer impresiones 3D te dejo un link para que puedas imprimir una carcasa en forma de cámara, mas adelante te dejo la imagen de como se vería).
* Si utilizas el Case, necesitarás tornillos a la medida [M2.5](https://www.adafruit.com/product/3299), necesitaremos de 12mm y 8mm de largo, aunque para aprovechar puedes comprar algunos de 10mm y 5mm pueden ser útiles para otros proyectos, los puedes conseguir en Amazon o tiendas especializadas en electrónica.

![20210502_132013](https://user-images.githubusercontent.com/79243784/117899439-be220c00-b28c-11eb-98ba-e935e9548107.jpg)

En caso hicieras uso del modelo 3D aquí tienes una imagen de cómo se vería, esta increíble no lo crees?

![raspberry_pi_hero-camera](https://user-images.githubusercontent.com/79243784/117897129-b4e27080-b287-11eb-80ee-47e0c8d58aa2.jpg)

Ahora hablaremos de los dos modulos que mencione.

### 1.1 HQ Camera module

Este módulo es el más reciente accesorio de cámara Raspberry Pi. Ofrece una resolución más alta (12 megapíxeles, en comparación con la anterior de 8 megapíxeles) y sensibilidad (aproximadamente un 50% más de área por píxel para rendimiento mejorado en condiciones de poca luz) que el módulo de cámara v2 existente, y está diseñado para funcionar con lentes intercambiables en montura C y CS. Se pueden utilizar otros lentes utilizando adaptadores.

Los lentes de 6 mm con montura CS y [16 mm](https://www.adafruit.com/product/4562) con montura C son ejemplos de todos los compatibles que existen.
La cámara de alta calidad ofrece una alternativa al módulo de cámara v2.

Para aplicaciones industriales y de consumo, incluidas cámaras de seguridad, que requieren los más altos niveles de fidelidad visual y/o integración con óptica especializada. Es compatible con todos los modelos de Raspberry Pi, la última versión de software.

![hq](https://user-images.githubusercontent.com/79243784/117897164-caf03100-b287-11eb-9407-56db4d3263ea.png)

![6mm](https://user-images.githubusercontent.com/79243784/117897186-d80d2000-b287-11eb-8dcd-02ce081d0dad.png)

### 1.2 Raspberry Pi Camera Board v2 (8 Mp)

Este módulo de cámara de 8 Mp es capaz de capturar video de 1080 px e imágenes, se puede conectar a todos los modelos de Raspberry Pi. Listo para conectar y usar, muy adecuado para fotografiar por lapsos, grabar video o para usarlo en aplicaciones de seguridad y en detección de movimientos. Sólo hay que conectar el cable incluido al puerto CSI de la Raspberry Pi.

El módulo es pequeño mide 25 mm x 23 mm x 9 mm y tiene una peso de 3 gr, haciéndola perfecta para aplicaciones móviles u otras en donde el peso es un factor muy importante.

El sensor tiene una resolución de 8 megapíxeles y tiene un lente de enfoque. En cuanto a las imágenes, la cámara es capaz de tomar imágenes estáticas hasta de 3280 x 2464 pixeles y videos de 1830p30.

![Sin título](https://user-images.githubusercontent.com/79243784/117897201-e0655b00-b287-11eb-846e-6095b8b03373.png)

## 2.Configuración de la cámara

### 2.1 Conexión física

Todos los modelos actuales de Raspberry Pi tienen un puerto para conectar el módulo de la cámara.

![pi4-camera-port](https://user-images.githubusercontent.com/79243784/117897214-e9eec300-b287-11eb-8152-bccb729a701f.png)

**Nota: Si desea utilizar una Raspberry Pi Zero, necesita un [cable](https://www.adafruit.com/product/3157) del módulo de la cámara que se ajuste al puerto del módulo de la cámara más pequeño de la Raspberry Pi Zero.**

Conecte el módulo de la cámara

**Asegúrese de que su Raspberry Pi esté apagada.**

1.   Localice el puerto del módulo de la cámara
2.   Tire suavemente hacia arriba de los bordes del clip de plástico del puerto
3. Inserte el cable plano del módulo de la cámara (**Nota: asegúrese de que el cable esté en la dirección correcta. El lado azul del cable va mirando hacia el conector jack y de los puertos USB**)
4. Vuelva a colocar el clip de plástico en su lugar.

![connect-camera](https://user-images.githubusercontent.com/79243784/117897272-0ee33600-b288-11eb-84ba-20752b986221.gif)

![ribon](https://user-images.githubusercontent.com/79243784/117897287-17d40780-b288-11eb-96c0-398930cd7a7a.png)

La forma mas simple de conectar el modulo HQ en mi caso se vería de la siguiente forma:

![20210502_140006](https://user-images.githubusercontent.com/79243784/117897301-20c4d900-b288-11eb-9883-a8efce9025d1.jpg)

Yo opté por solamente utilizar el soporte de la cámara con la Raspberry por lo que te mostraré un poco de cómo utilice los tornillos y el resultado final.

![20210502_134233](https://user-images.githubusercontent.com/79243784/117897329-2d493180-b288-11eb-8a0b-1c9b9c9ad448.jpg)

![20210506_110038](https://user-images.githubusercontent.com/79243784/117897371-4651e280-b288-11eb-995f-37b537db8003.jpg)

![20210506_110052](https://user-images.githubusercontent.com/79243784/117897377-494cd300-b288-11eb-9d14-ce4cdfdc21ee.jpg)

Ahora solo faltaría conectar el lente que en esta ocasión utilicé el de 6mm, puedes saltarte esta parte y pasar a la parte 2.2 si es que utilizaste la opción V2 de 8 Mp.

![Diseño sin título](https://user-images.githubusercontent.com/79243784/117898228-1efc1500-b28a-11eb-80e9-aa66eab0fb87.png)

Tenemos que quitar la tapa anti-polvo para el lente de 6mm y el adaptador C-CS entonces nos quedaría de la siguiente forma:

![hq](https://user-images.githubusercontent.com/79243784/117898246-27545000-b28a-11eb-858b-39e55220f7d6.png)

Los lentes vienen con dos tapas una del lado del lente y otra por la entrada que conecta al modulo.

#### 2.1.1 Colocación del lente
La lente de 6 mm tiene montura CS,
por lo que no necesita el anillo adaptador C-CS. No se enfocará correctamente si el adaptador está instalado, así que, si es necesario, retírelo.
Luego, gire la lente en el sentido de las agujas del reloj hasta el final para dejarlo conectactado con el anillo de ajuste del enfoque posterior. **No debe apretarse con mucha fuerza por que puedes dañar el lente o el modulo, solamente que quede firme.**

![gira](https://user-images.githubusercontent.com/79243784/117899476-d003af00-b28c-11eb-80fd-3747125546ba.png)

#### 2.1.2 Ajuste de enfoque anillo posterior y tornillo de bloqueo
El anillo de ajuste del enfoque posterior debe estar atornillado completamente para la distancia focal posterior más corta posible. Utilice el tornillo de bloqueo del enfoque posterior para
asegúrarse de que no se mueva de esta posición al ajustar la apertura o el enfoque (Al comprar el modulo HQ incluye un atornillador de la medida exacta para poder manipular el tornillo de bloqueo).

![atornilla](https://user-images.githubusercontent.com/79243784/117899492-d7c35380-b28c-11eb-9de1-ac270723cc5c.png)

Ya listo e instalado nuestro lente se verá de la siguiente forma.

![20210502_143918](https://user-images.githubusercontent.com/79243784/117899502-de51cb00-b28c-11eb-95db-ceb0a9a4c218.jpg)

Una vez ya instalado el lente y conectado el módulo a nuestra Raspberry podemos seguir con la configuración al encender e ingresar por VNC.

### 2.2 Configuración de Raspberry Pi por VNC.

1.   Enciende tu Raspberry Pi.
2.   Ingresa por VNC desde tu ordenador a tu Raspberry.
3.   Vaya al menú principal y abra **Raspberry Pi Configuration**.

![pi-configuration-menu](https://user-images.githubusercontent.com/79243784/117899529-eb6eba00-b28c-11eb-978c-ff27014dc510.png)

Seleccione la pestaña **Interfaces** y asegúrese de que la cámara esté habilitada (**enabled**)

![1CAMERAENABLE](https://user-images.githubusercontent.com/79243784/117899553-fb869980-b28c-11eb-9493-c81c301eb4ad.png)

Reinicia tu Raspberry Pi.

![3](https://user-images.githubusercontent.com/79243784/117899579-07725b80-b28d-11eb-950b-b470adfe0725.png)

Una vez reiniciada, pasaremos a hacer unos cambios en VNC dentro del escritorio de Raspberry, al ejecutar algunos comandos nos mostrará la vista previa de lo que va a capturar en VNC no es posible a menos de que hagamos estos cambios. Lo primero es dirigirnos al icono de VNC y dar clic.

![TERMINAL](https://user-images.githubusercontent.com/79243784/117899610-1822d180-b28d-11eb-8eef-fa20be6bc57b.png)

Nos abrirá la siguiente ventana, donde encontraremos en la parte derecha un recuadro daremos clic.

![VNC1](https://user-images.githubusercontent.com/79243784/117899631-2244d000-b28d-11eb-9a9a-0956f03f07f7.png)

Daremos clic en "Options".

![options](https://user-images.githubusercontent.com/79243784/117899691-41dbf880-b28d-11eb-992a-ff5dfc4319e0.png)

Nos iremos a la pestaña "Troubleshooting"

![2021-05-02-152414_1024x768_scrot](https://user-images.githubusercontent.com/79243784/117899707-4c968d80-b28d-11eb-8bbc-bdfe6de2db8a.png)

Daremos clic en la casilla "Enable direct capture mode" y después daremos clic en Apply . Esto nos permitirá ver la vista previa de lo que está capturando nuestro modulo cámara. Se irá a pantalla negra unos segundos y cuando recupere la imagen estará listo, no es necesario pero puedes reiniciar la Raspberry para comenzar con el siguiente paso.

![2021-05-02-152426_1024x768_scrot](https://user-images.githubusercontent.com/79243784/117899734-56b88c00-b28d-11eb-9962-24a4284477c3.png)

Por el momento la cámara está desenfocada así que necesitamos ejecutar un comando para poder tener acceso a la vista. Así que vamos a abrir la terminal de Raspberry.

![4TERMINAL](https://user-images.githubusercontent.com/79243784/117899764-67690200-b28d-11eb-9682-b7aa59ed2026.png)

raspistill es una herramienta de comandos para capturar imágenes de la cámara. Para verificar que la cámara está instalada correctamente y usar la cámara sólo como un visor, sin guardar una foto, ingresa este
comando:
 
`raspistill -t 0`
 
Nos dará de seguro una imagen borrosa en el caso del modulo HQ para el módulo V2 no tendrá mayor problema.

![6](https://user-images.githubusercontent.com/79243784/117899782-78197800-b28d-11eb-9604-5398440d1484.png)

Ahora veremos los pasos para enfocar el modulo con su lente.

![yes](https://user-images.githubusercontent.com/79243784/117899834-941d1980-b28d-11eb-90ff-37ee60122136.png)

#### 2.2.1 Apertura
Para arreglar esto hay que ajustar la apertura, mantenga la cámara con el objetivo en dirección opuesta a usted.
Gire el anillo del medio mientras sostiene el anillo exterior, más alejado de la cámara, estable. Turno en el sentido de las agujas del reloj para cerrar la apertura y reducir brillo de la imagen. Gire en sentido antihorario para abrir la apertura. Una vez que estés feliz con la luz nivel, apriete el tornillo en el lateral de la lente para bloquear la apertura.

![aprtura](https://user-images.githubusercontent.com/79243784/117899916-caf32f80-b28d-11eb-8b90-2671931d9ea0.png)

#### 2.2.2 Enfoque 
Primero, bloquee el anillo de enfoque interno, etiquetado
"NEAR FAR", en posición apretando su tornillo. Ahora sostenga la cámara con la lente de espaldas a ti. Sostenga los dos exteriores anillos de la lente y gírese en el sentido de las agujas del reloj
hasta que la imagen esté enfocada, tomará cuatro o cinco vueltas enteras. Para ajustar el enfoque, gire los dos anillos exteriores en el sentido de las agujas del reloj para enfocar un objeto cercano. Gire en sentido antihorario para centrarse en un objeto distante.Lo mas seguro es que necesitarás ajustar la apertura nuevamente después de esto cada que quites y pongas el lente.

![enfoque](https://user-images.githubusercontent.com/79243784/117899921-cfb7e380-b28d-11eb-9df7-b3492bb27ae9.png)

Después de enfocar, tendremos que cerrar la ventana, tal vez no podamos por que la imagen es muy grande y no aparece el icono de cerrar, en ese caso tendremos que acceder por SSH y usar el comando:
 
```
sudo reboot
```
Para poder acceder de nuevo por VNC.

#### 2.2.3 Prueba imagen.jpg

Ahora deberías ver una imagen clara y podrás tomar una fotografía de prueba ingresando el comando:

`raspistill -o test.jpg`

Cuando presione ENTER, aparecerá una imagen de vista previa en vivo, y después de un período predeterminado de cinco segundos, la cámara capturará una única imagen fija. Esto se guardará en su carpeta de inicio y llamado test.jpg.

![2021-05-02-162452_1024x768_scrot](https://user-images.githubusercontent.com/79243784/117899956-e3fbe080-b28d-11eb-8c27-5245ed3c0925.png)

Así se ve la imagen que tomé con este comando:

![test](https://user-images.githubusercontent.com/79243784/117899972-ebbb8500-b28d-11eb-943b-24779509291d.jpg)

#### 2.2.4 Prueba video
 
Para grabar videos, raspivid es lo que necesitas. Pruébalo con este comando de Terminal:
 
-t 10000 es el tiempo que va a estar grabando video, 10000 milisegundos serían 10 segundos de grabación. h264 es el formato de video para reproducir en vlc, reproductor que incluye el Raspberry Pi OS, en caso de que quieras cambiar el formato por MP4 que es un formato más común y amigable para edición, al final te dejare algunos comandos y ligas para esto.
 
```
raspivid -t 10000 -o testvideo.h264
```
![2021-05-06-111139_1024x768_scrot](https://user-images.githubusercontent.com/79243784/117900055-1279bb80-b28e-11eb-8f5a-b4b876977c78.png)

Podremos ver la vista previa del archivo y después en la carpeta de Raspberry Pi encontraremos el archivo para poder reproducirlo.

![2021-05-06-111916_1024x768_scrot](https://user-images.githubusercontent.com/79243784/117900127-33daa780-b28e-11eb-8b73-11dc4ae42a53.png)

## 3.Controlar el módulo de la cámara con código Python

### 3.1 Vista previa

La biblioteca Python ***picamera*** le permite controlar su módulo de cámara y crear proyectos increíbles.
 
Abra un editor de Python 3, como Thonny Python IDE o aprovechando el tutorial anterior [VS Code en Raspberry Pi](https://github.com/fullmakeralchemist/gitvscode) podemos usar el VS Code, crearemos una  carpeta en el escritorio llamada camera o cámara, daremos clic derecho para abrir las opciones, seleccionaremos "Open current folder in terminal", para abrir directamente el folder y la terminal, también puedes hacer esto en la terminal con el comando cd para ubicarnos en la carpeta camera.
 
Una vez ubicados en dentro de la terminal en la carpeta utilizaremos el comando:
 
`code .`
 
Con esto nos abrirá directamente VS Code en la carpeta que vamos a trabajar

![2021-05-06-112129_1024x768_scrot](https://user-images.githubusercontent.com/79243784/117911744-ea955280-b2a3-11eb-88b5-0d1e7c93538d.png)

Abra un archivo nuevo y guárdelo como camera.py.

**Nota: es importante que nunca guarde el archivo como picamera.py**

En VS code podemos encontrar el icono de crear nuevo archivo.

![2021-05-06-112835_1024x768_scrot2](https://user-images.githubusercontent.com/79243784/117911776-f7b24180-b2a3-11eb-8e12-05c0edde9720.png)

Ahora daremos clic en "CTRL + S" para guardar y nos aparecerá la siguiente ventana. Ingresamos el nombre de nuestro archivo para poder ingresar el código.

![2021-05-06-112636_1024x768_scrot](https://user-images.githubusercontent.com/79243784/117911796-ff71e600-b2a3-11eb-8420-fec124acae41.png)

Antes de ingresar el código debemos asegurarnos de tener instalada la herramienta de Python para VS Code. Verifique con la imagen que tiene instalada la que utilizaremos.

![2021-05-06-112745_1024x768_scrot](https://user-images.githubusercontent.com/79243784/117911819-0ac51180-b2a4-11eb-9ce1-30132e636553.png)

Ingrese el siguiente código que nos permitirá hacer la misma función de darnos una imagen previa para verificar que nuestro lente está enfocado si ya hiciste este paso y no has desconectado la cámara puedes omitir este paso y pasar al siguiente código:

```
from picamera import PiCamera     #importa paquete
from time import sleep

camera = PiCamera()    #Primero, importamos la clase PiCamera del módulo picamera. 
                       #Usaremos esa clase para tener acceso a la cámara física.

camera.start_preview()      #método para iniciar la visualización de la entrada de la cámara.
sleep(5)                    #tiempo que esta abierta la visualización
camera.stop_preview()       #método para cerrar la visualización de la entrada de la cámara.
```

![2021-05-06-112645_1024x768_scrot](https://user-images.githubusercontent.com/79243784/117911877-20d2d200-b2a4-11eb-87e4-2a73cbf38d04.png)

Usamos “CRTL + S” para guardar y ahora abriremos una terminal en VS Code para este proyecto.

![2021-05-06-112652_1024x768_scrot](https://user-images.githubusercontent.com/79243784/117911909-2d572a80-b2a4-11eb-97fe-c0f2f11e2b42.png)

Ahora podremos ver la terminal en la parte inferior y solo necesitamos correr las líneas de código con el botón que tiene el VS Code en la parte superior derecha (También puedes hacer esto desde la terminal de la forma tradicional y utilizar el comando: `sudo python3 camera.py`)

![2021-05-06-112828_1024x768_scrot](https://user-images.githubusercontent.com/79243784/117911958-4069fa80-b2a4-11eb-89d5-07140390f9ec.png)

Podrás ver en la parte inferior la ejecución del comando.

![2021-05-06-112845_1024x768_scrot](https://user-images.githubusercontent.com/79243784/117912047-65f70400-b2a4-11eb-83ba-c0b5066ff8ba.png)

Al ejecutarse abrira una ventana muy grande que cerrara a los 5 segundos como tenemos definido en `sleep(5)`, tenemos que definir un tiempo si no se mantendra abierta la ventana como en `raspistill -t 0` entonces tendriamos que usar el SSH para ingresar el comando `sudo reboot` para ingresar nuevamente y seguir con el siguiente codigo.

### 3.2 Fotografia 

Ahora para tomar algunas fotografías puede crear un segundo archivo en mi caso lo llame cameratake.py, modifique su código para agregar una línea camera.capture ():

```
from picamera import PiCamera 
from time import sleep 
camera = PiCamera()
camera.start_preview() 
sleep(5)   
camera.capture('/home/pi/Desktop/image.jpg')        #directorio en el que va a guardar la imagen y 
                                                    #el nombre de la imagen
camera.stop_preview() 
```
**Nota: es importante usar un sleep de al menos dos segundos antes de capturar una imagen, porque esto le da tiempo al sensor de la cámara para detectar los niveles de luz.**

Ejecutar con el botón de VS Code.

![2021-05-06-113114_1024x768_scrot](https://user-images.githubusercontent.com/79243784/117912105-7c04c480-b2a4-11eb-8b48-581f6890fc03.png)

Debería ver la vista previa de la cámara abierta durante cinco segundos y luego se debe capturar una imagen fija. Mientras se toma la imagen, puede ver la vista previa ajustarse brevemente a una resolución diferente.

Su nueva imagen debe guardarse en el escritorio.

![2021-05-06-113130_1024x768_scrot](https://user-images.githubusercontent.com/79243784/117912123-845cff80-b2a4-11eb-8af0-660d60e44983.png)

### 3.3 Video

¡Ahora graba un video!

Modifique su código para eliminar capture() y en su lugar agregue start_recording() y stop_recording(). Su código debería verse así ahora:

```
from picamera import PiCamera
from time import sleep
camera = PiCamera()
camera.start_preview()
camera.start_recording('/home/pi/video.h264') #directorio en el que va a guardar el 
                                              #video y el nombre del archivo
sleep(10)
camera.stop_recording()
camera.stop_preview()
```

![2021-05-06-113254_1024x768_scrot](https://user-images.githubusercontent.com/79243784/117912188-a9ea0900-b2a4-11eb-95cf-0fcbfac78e42.png)

Ejecute el código.

Su Raspberry Pi debería abrir una vista previa, grabar 5 segundos de video y luego cerrar la vista previa.

![2021-05-06-113306_1024x768_scrot](https://user-images.githubusercontent.com/79243784/117912196-aeaebd00-b2a4-11eb-8afb-f2af40f56fcc.png)

# 4.Extras

## 4.1 Formato de video MP4

Raspberry Pi captura video como un formato de video H264 sin procesar. Muchos reproductores multimedia se negarán a reproducirlo, o lo reproducirá a una velocidad incorrecta, a menos que esté "envuelto" en un formato contenedor adecuado como MP4. La forma más fácil de obtener un archivo MP4 con el comando raspivid es usando MP4Box.

Instale MP4Box con este comando:

```
sudo apt install -y gpac
```

Capture su video sin procesar con raspivid y envuélvalo en un contenedor MP4 como este:

```
# Capture 30 segundos de video sin procesar a 640x480 y una tasa de bits de 150kB/s en un archivo pivideo.h264:
raspivid -t 30000 -w 640 -h 480 -fps 25 -b 1200000 -p 0,0,640,480 -o pivideo.h264
# Envuelva el video sin procesar con un contenedor MP4:
MP4Box -add pivideo.h264 pivideo.mp4
# Elimina el archivo sin procesar de origen, dejando que se reproduzca el archivo pivideo.mp4 restante
rm pivideo.h264
```

Alternativamente, envuelva el formato MP4 alrededor de su salida raspivid existente, con:

```
MP4Box -add video.h264 video.mp4
```




Con esto llegamos al fin de esta guía, puedes aprovechar la [guía de Git y VS Code](https://github.com/fullmakeralchemist/gitvscode) para subir estos códigos a tu Github, para revisar mas sobre el formato MP4 en Raspberry visita [raspivid](https://www.raspberrypi.org/documentation/usage/camera/raspicam/raspivid.md).

Sí quieres saber mas sobre Raspberry Pi y el uso de la cámara visita [Camera Raspberry Pi](https://projects.raspberrypi.org/en/projects/getting-started-with-picamera/6).

Visita mi repositorio en Github.
