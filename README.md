# Raspberry Camera Setup

One of the most used applications in Raspberry is the use of cameras, to use Tensorflow and give it the ability to detect objects. Now that the Raspberry Pi is fast enough to perform machine learning, adding these functions in projects is easier.
 
This guide will show you the steps to learn how to connect the Raspberry Pi camera module, take pictures, record videos, and apply image effects.
 
It is important to know the camera module well before starting to create our applications.
 
Without more to say let's get started.

## 1.What you'll need

There are multiple options but in this guide I will give you two options so that you can choose the one that you like the most, on the part of Raspberry Pi there are two camera modules I will talk about them later.
 
*   Laptop
*   Raspberry Pi 4
*   Power supply (Preferably purchase the official source together with your Raspberry so as not to have any problems, if you do not have much experience [USB-C Power Supply](https://www.raspberrypi.org/products/type-c-power-supply/))
* Smartphone with Mobile Hotspot function
*  Micro SD card
*  [Raspberry Pi High Quality Camera](https://www.adafruit.com/product/4561) (is the one I will use in this guide, but you can use the [Raspberry Pi Camera Board v2](https://www.adafruit.com/product/3099) It is the previous and cheaper version)
* [6mm 3MP Wide Angle Lens for Raspberry Pi HQ Camera - 3MP](https://www.adafruit.com/product/4563) (The HQ camera module allows us to use lenses, this element is optional in case of using the second camera option)
* [Flex Cable for Raspberry Pi Camera](https://www.adafruit.com/product/2087) (It is usually included in the purchase of Raspberry Pi Camera modules)
* Camera tripod (**Note: only in case of using the HQ module.** The advantage of the HQ module is that it has a standard 1/4 ”-20 tripod mount, which is what most of the the current tripods, I leave you a link of a purchase option in [Amazon](https://www.amazon.com.mx/Ubeesize-tel%C3%A9fono-ajustable-distancia-Universal/dp/B06Y2VP3C7/ref=sr_1_3?__mk_es_MX=%C3%85M%C3%85%C5%BD%C3%95%C3%91&dchild=1&keywords=%C2%BC%22-20+tripod&qid=1620010127&refinements=p_36%3A9841539011&rnid=9754432011&s=electronics&sr=1-3))
 
Optional:
* [Raspberry Pi HQ Camera Case](https://learn.adafruit.com/raspberry-pi-hq-camera-case/3d-printing) (In case you have a 3D printer or make 3D prints I leave you a link so you can print a camera-shaped housing, later I leave you the image of how it would look).

* If you use the Case, you will need custom screws [M2.5](https://www.adafruit.com/product/3299), We will need 12mm and 8mm long, although to take advantage you can buy some 10mm and 5mm they can be useful for other projects, you can get them at Amazon or specialized electronics stores.

![20210502_132013](https://user-images.githubusercontent.com/79243784/117899439-be220c00-b28c-11eb-98ba-e935e9548107.jpg)

In case you made use of the 3D model, here you have an image of what it would look like, this incredible, don't you think?

![raspberry_pi_hero-camera](https://user-images.githubusercontent.com/79243784/117897129-b4e27080-b287-11eb-80ee-47e0c8d58aa2.jpg)

Now we will talk about the two modules that I mentioned.

### 1.1 HQ Camera module

This module is the latest Raspberry Pi camera accessory. It offers higher resolution (12 megapixels, compared to the previous 8 megapixels) and sensitivity (approximately 50% more area per pixel for improved performance in low light conditions) than the existing v2 camera module, and is designed to work with interchangeable C and CS mount lenses. Other lenses can be used using adapters.

6mm CS mount lenses and [16 mm](https://www.adafruit.com/product/4562) with C-mount are examples of all the compatible ones that exist.
The high-quality camera offers an alternative to the camera module v2.

For industrial and consumer applications, including security cameras, that require the highest levels of visual fidelity and / or integration with specialized optics. It is compatible with all Raspberry Pi models, the latest version of software.

![hq](https://user-images.githubusercontent.com/79243784/117897164-caf03100-b287-11eb-9407-56db4d3263ea.png)

![6mm](https://user-images.githubusercontent.com/79243784/117897186-d80d2000-b287-11eb-8dcd-02ce081d0dad.png)

### 1.2 Raspberry Pi Camera Board v2 (8 Mp)

This 8 Mp camera module is capable of capturing 1080 px video and images, it can be connected to all Raspberry Pi models. Ready to plug and play, well suited for lap photography, video recording, or for use in security and motion detection applications. Just connect the included cable to the CSI port of the Raspberry Pi.

The module is small measuring 25 mm x 23 mm x 9 mm and has a weight of 3 grams, making it perfect for mobile applications or others where weight is a very important factor.

The sensor has a resolution of 8 megapixels and has a focusing lens. As for images, the camera is capable of taking still images up to 3280 x 2464 pixels and 1830p30 videos.

![Sin título](https://user-images.githubusercontent.com/79243784/117897201-e0655b00-b287-11eb-846e-6095b8b03373.png)

## 2.Camera setup

### 2.1 Connection

All current Raspberry Pi models have a port to connect the camera module.

![pi4-camera-port](https://user-images.githubusercontent.com/79243784/117897214-e9eec300-b287-11eb-8152-bccb729a701f.png)

**Note: If you want to use a Raspberry Pi Zero, you need a camera module [cable](https://www.adafruit.com/product/3157) that fits into the smaller camera module port of the Raspberry Pi Zero.**

Connect the camera module

**Make sure your Raspberry Pi is powered off.**

1.   Locate the camera module port
2.   Gently pull up on the edges of the plastic port clip
3.   Insert the flat cable from the camera module (**Note: Make sure the cable is in the correct direction. The blue side of the cable is facing the jack connector and the USB ports**)
4.   Put the plastic clip back in place.

![connect-camera](https://user-images.githubusercontent.com/79243784/117897272-0ee33600-b288-11eb-84ba-20752b986221.gif)

![ribon](https://user-images.githubusercontent.com/79243784/117897287-17d40780-b288-11eb-96c0-398930cd7a7a.png)

The simplest way to connect the HQ module in my case would look like this:

![20210502_140006](https://user-images.githubusercontent.com/79243784/117897301-20c4d900-b288-11eb-9883-a8efce9025d1.jpg)

I opted to only use the camera mount with the Raspberry so I'll show you a bit of how to use the screws and the end result.

![20210502_134233](https://user-images.githubusercontent.com/79243784/117897329-2d493180-b288-11eb-8a0b-1c9b9c9ad448.jpg)

![20210506_110038](https://user-images.githubusercontent.com/79243784/117897371-4651e280-b288-11eb-995f-37b537db8003.jpg)

![20210506_110052](https://user-images.githubusercontent.com/79243784/117897377-494cd300-b288-11eb-9d14-ce4cdfdc21ee.jpg)

Now I just need to connect the lens that this time I used the 6mm one, you can skip this part and go to part 2.2 if you used the 8 Mp V2 option.

![Diseño sin título](https://user-images.githubusercontent.com/79243784/117898228-1efc1500-b28a-11eb-80e9-aa66eab0fb87.png)

We have to remove the dust cap for the 6mm lens and the C-CS adapter so it would be as follows:

![hq](https://user-images.githubusercontent.com/79243784/117898246-27545000-b28a-11eb-858b-39e55220f7d6.png)

The lenses come with two covers, one on the side of the lens and the other through the entrance that connects to the module.

#### 2.1.1 Fitting the lens
6mm lens is CS mount,
so you don't need the C-CS adapter ring. It will not focus properly if the adapter is installed, so remove it if necessary.
Then turn the lens clockwise all the way to connect it with the back focus adjustment ring. **It should not be tightened with too much force because you can damage the lens or the module, just keep it firm.**

![gira](https://user-images.githubusercontent.com/79243784/117899476-d003af00-b28c-11eb-80fd-3747125546ba.png)

#### 2.1.2 Back focus adjustment ring and lock screw
The back focus adjustment ring should be fully screwed in for the shortest possible back focal length. Use the back focus locking screw to make sure that it does not move from this position when adjusting the aperture or focus (When purchasing the HQ module, it includes a screwdriver of the exact size to be able to manipulate the locking screw).

![atornilla](https://user-images.githubusercontent.com/79243784/117899492-d7c35380-b28c-11eb-9de1-ac270723cc5c.png)

Once ready and installed, our lens will look like the following.

![20210502_143918](https://user-images.githubusercontent.com/79243784/117899502-de51cb00-b28c-11eb-95db-ceb0a9a4c218.jpg)

Once the lens is installed and the module is connected to our Raspberry, we can continue with the configuration when turning on and entering through VNC.

### 2.2 Raspberry Pi configuration by VNC.

1.   Turn on your Raspberry Pi.
2.   Login via VNC from your computer to your Raspberry.
3.   Go to the main menu and open **Raspberry Pi Configuration**.

![pi-configuration-menu](https://user-images.githubusercontent.com/79243784/117899529-eb6eba00-b28c-11eb-978c-ff27014dc510.png)

Select the **Interfaces** tab and make sure the camera is **enabled**.

![1CAMERAENABLE](https://user-images.githubusercontent.com/79243784/117899553-fb869980-b28c-11eb-9493-c81c301eb4ad.png)

Reboot your Raspberry Pi.

![3](https://user-images.githubusercontent.com/79243784/117899579-07725b80-b28d-11eb-950b-b470adfe0725.png)

Once restarted, we will make some changes in VNC within the Raspberry desktop, when executing some commands it will show us the preview of what it is going to capture in VNC it is not possible unless we make these changes. The first thing is to go to the VNC icon and click.

![TERMINAL](https://user-images.githubusercontent.com/79243784/117899610-1822d180-b28d-11eb-8eef-fa20be6bc57b.png)

The following window will open, where we will find a box on the right side, we will click.

![VNC1](https://user-images.githubusercontent.com/79243784/117899631-2244d000-b28d-11eb-9a9a-0956f03f07f7.png)

We will click on "Options".

![options](https://user-images.githubusercontent.com/79243784/117899691-41dbf880-b28d-11eb-992a-ff5dfc4319e0.png)

We will go to the tab "Troubleshooting".

![2021-05-02-152414_1024x768_scrot](https://user-images.githubusercontent.com/79243784/117899707-4c968d80-b28d-11eb-8bbc-bdfe6de2db8a.png)

We will click on the "Enable direct capture mode" box and then we will click on Apply. This will allow us to see the preview of what our camera module is capturing. It will go to black screen for a few seconds and when it recovers the image it will be ready, it is not necessary but you can restart the Raspberry to start with the next step.

![2021-05-02-152426_1024x768_scrot](https://user-images.githubusercontent.com/79243784/117899734-56b88c00-b28d-11eb-9962-24a4284477c3.png)

At the moment the camera is out of focus so we need to run a command to access the view. So let's open the Raspberry terminal.

![4TERMINAL](https://user-images.githubusercontent.com/79243784/117899764-67690200-b28d-11eb-9682-b7aa59ed2026.png)

raspistill is a command tool for capturing images from the camera. To verify that the camera is installed correctly and use the camera only as a viewfinder, without saving a photo, enter this
command:
 
`raspistill -t 0`
 
It will give us a blurry image for sure in the case of the HQ module for the V2 module it will not have a major problem.

![6](https://user-images.githubusercontent.com/79243784/117899782-78197800-b28d-11eb-9604-5398440d1484.png)

Now we will see the steps to focus the module with its lens.

![yes](https://user-images.githubusercontent.com/79243784/117899834-941d1980-b28d-11eb-90ff-37ee60122136.png)

#### 2.2.1 Aperture
To fix this you have to adjust the aperture, keep the camera with the lens away from you.
Rotate the middle ring while holding the outer ring, farthest from the camera, stable. Shift clockwise to close the aperture and reduce image brightness. Turn counterclockwise to open the opening. Once you are happy with the light level, tighten the screw on the side of the lens to lock the aperture.

![aprtura](https://user-images.githubusercontent.com/79243784/117899916-caf32f80-b28d-11eb-8b90-2671931d9ea0.png)

#### 2.2.2 Focus 
First, lock the inner focus ring, labeled
"NEAR FAR", in position by tightening its screw. Now hold the camera with the lens facing away from you. Hold the two outer rings of the lens and turn clockwise until the image is in focus, it will take four or five full turns. To adjust the focus, turn the two outer rings clockwise to focus on a nearby object. Rotate counterclockwise to focus on a distant object - you will most likely need to adjust the aperture again after this each time you remove and attach the lens.

![enfoque](https://user-images.githubusercontent.com/79243784/117899921-cfb7e380-b28d-11eb-9df7-b3492bb27ae9.png)

After focusing, we will have to close the window, maybe we cannot because the image is very large and the close icon does not appear, in that case we will have to access by SSH and use the command:
 
```
sudo reboot
```
To be able to access again by VNC.

#### 2.2.3 Test image.jpg

You should now see a clear image and you can take a test photo by entering the command:

`raspistill -o test.jpg`

When you press ENTER, a live preview image will appear, and after a predetermined period of five seconds, the camera will capture a single still image. This will be saved in your home folder and named test.jpg.

![2021-05-02-162452_1024x768_scrot](https://user-images.githubusercontent.com/79243784/117899956-e3fbe080-b28d-11eb-8c27-5245ed3c0925.png)

This is what the image I took with this command looks like:

![test](https://user-images.githubusercontent.com/79243784/117899972-ebbb8500-b28d-11eb-943b-24779509291d.jpg)

#### 2.2.4 Video test
 
To record videos, raspivid is what you need. Try it with this Terminal command:
 
-t 10000 is the time that it will be recording video, 10000 milliseconds would be 10 seconds of recording. h264 is the video format to play in vlc, a player that includes the Raspberry Pi OS, in case you want to change the format to MP4 which is a more common and friendly format for editing, at the end I will leave you some commands and links for this .
 
```
raspivid -t 10000 -o testvideo.h264
```
![2021-05-06-111139_1024x768_scrot](https://user-images.githubusercontent.com/79243784/117900055-1279bb80-b28e-11eb-8f5a-b4b876977c78.png)

We can see the preview of the file and then in the Raspberry Pi folder we will find the file to be able to reproduce it.

![2021-05-06-111916_1024x768_scrot](https://user-images.githubusercontent.com/79243784/117900127-33daa780-b28e-11eb-8b73-11dc4ae42a53.png)

## 3.Control the camera module with Python code

### 3.1 Preview

The Python ***picamera*** library allows you to control your camera module and create amazing projects.
 
Open a Python 3 editor, such as Thonny Python IDE or taking advantage of the previous tutorial [VS Code on Raspberry Pi](https://github.com/fullmakeralchemist/gitvscode) we can use the VS Code, we will create a folder on the desktop called camera or camera, we will right click to open the options, we will select "Open current folder in terminal", to directly open the folder and the terminal, you can also do this in the terminal with the cd command to locate ourselves in the camera folder.
 
Once located inside the terminal in the folder we will use the command:
 
`code .`
 
With this we will directly open VS Code in the folder that we are going to work with

![2021-05-06-112129_1024x768_scrot](https://user-images.githubusercontent.com/79243784/117911744-ea955280-b2a3-11eb-88b5-0d1e7c93538d.png)

Open a new file and save it as camera.py.

**Note: it is important that you never save the file as picamera.py**

In VS code we can find the icon to create a new file.

![2021-05-06-112835_1024x768_scrot2](https://user-images.githubusercontent.com/79243784/117911776-f7b24180-b2a3-11eb-8e12-05c0edde9720.png)

Now we will click on "CTRL + S" to save and the following window will appear. We enter the name of our file to be able to enter the code.

![2021-05-06-112636_1024x768_scrot](https://user-images.githubusercontent.com/79243784/117911796-ff71e600-b2a3-11eb-8420-fec124acae41.png)

Before entering the code we must make sure that we have the Python tool for VS Code installed. Verify with the image that you have installed the one that we will use.

![2021-05-06-112745_1024x768_scrot](https://user-images.githubusercontent.com/79243784/117911819-0ac51180-b2a4-11eb-9ce1-30132e636553.png)

Enter the following code that will allow us to do the same function of giving us a preview image to verify that our lens is in focus. If you have already done this step and have not disconnected the camera, you can skip this step and go to the following code:

```
from picamera import PiCamera     #import package
from time import sleep

camera = PiCamera()    #First, we import the PiCamera class from the picamera module.
                       # We will use that class to access the physical camera.

camera.start_preview()      # method to start the camera input display.
sleep(5)                    #time the visualization is open
camera.stop_preview()       # method to close the camera input display.
```

![2021-05-06-112645_1024x768_scrot](https://user-images.githubusercontent.com/79243784/117911877-20d2d200-b2a4-11eb-87e4-2a73cbf38d04.png)

We use "CRTL + S" to save and now we will open a terminal in VS Code for this project.

![2021-05-06-112652_1024x768_scrot](https://user-images.githubusercontent.com/79243784/117911909-2d572a80-b2a4-11eb-97fe-c0f2f11e2b42.png)

Now we can see the terminal at the bottom and we only need to run the lines of code with the button that has the VS Code in the upper right (You can also do this from the terminal in the traditional way and use the command: `sudo python3 camera.py`)

![2021-05-06-112828_1024x768_scrot](https://user-images.githubusercontent.com/79243784/117911958-4069fa80-b2a4-11eb-89d5-07140390f9ec.png)

You can see at the bottom the execution of the command.

![2021-05-06-112845_1024x768_scrot](https://user-images.githubusercontent.com/79243784/117912047-65f70400-b2a4-11eb-83ba-c0b5066ff8ba.png)

When executed, it will open a very large window that will close after 5 seconds as we have defined in `sleep (5)`, we have to define a time if the window will not remain open as in `raspistill -t 0` then we would have to use SSH to enter the command `sudo reboot` to enter again and continue with the next code.

### 3.2 Photo

Now to take some pictures you can create a second file in my case call it cameratake.py, modify your code to add a camera.capture () line:

```
from picamera import PiCamera
from time import sleep

camera = PiCamera()

camera.start_preview()
sleep(5)
camera.capture('/home/pi/Desktop/image.jpg')  #directory where you will save the image and the name of the image
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
