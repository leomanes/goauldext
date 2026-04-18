# goauldext
40 pin extension for the MSX Goa'uld / 3.58MHz clock gen

This is an extension to allow the MSX Goa'uld (Tang Nano 20K) to be installed away from the z80 socket.

The PCB can also be installed on the VDP socket and configured to generate the 3.58MHz clock.

Below you see the same PCB being used connected to the Tang Nano 20K (yellow box left), to the Z80 socket (yellow box right) and replacing the VDP that generates the 3.58MHz clock (red box).

<img width="1583" height="1078" alt="image" src="https://github.com/user-attachments/assets/46ef58d3-06aa-42e3-b49e-743d15e26327" />

CONFIGURING THE EXTENSION:

NOTES:

THE PCB THAT WILL BE INSTALLED ON THE Z80 SOCKET WILL ALWAYS HAVE THE 40 pins ZIFF CONNECTOR SOLDERED AT THE **TOP** OF THE PCB

THE PCB THAT WILL RECEIVE THE TANG NANO 20 WILL HAVE ITS SOCKET INSTALLED ON THE **UNDERSIDE** OF THE PCB.

THE MAX RECOMEND LENGHT OF THE 40 PIN FLEX CABLE IS 20CM. THERE ARE REPORTS OF SUCESS WITH 30CM BUT YOU MIGHT RUN INTO INSTABILIBTIES.

THE EXTENTION ONLY NEED THE ZIFF CONNECTORS.

      

ATENTION: IF YOU DON'T CONFIGURE YOUR EXTENTION CORRECTLY YOU MIGHT DAMAGE YOUR MSX MACHINE AND/OR THE TANG NANO.

<img width="744" height="1675" alt="image" src="https://github.com/user-attachments/assets/a2e3fd41-0a71-4e50-96ca-8776aa0ea3ff" />


 
1) Plug the PCB on the Z80 socket (the PCB with the ZIFF at the top as explained above) in a way that the flex cable runs to the direction you want it to go).
   
2) LOCATE YOUR Z80 PIN 1... what letter is conected to on the PCB?  Letter A or B?
   
3) Now plug/solder yor Tang Nano 20K making sure its PIN 1 also lands on the letter found above.


So if Z80 pin 1 is on A, the Tang Nano pin 1 will also be on the letter A.

If Z80 pin 1 on B... Tang Nano ping one will also be on B.

* If the HDMI is not facing the direction you want... I am sorry. You will probably need a HDMI flex extention anyways so you can get away by using one.

4) Now that you know your letter, close JP1 LEFT + CENTER solder jumper (GLD side).
   
5) Also close JP3 solder jumper based on the letter of your installation (A=LEFT + CENTER) or (B=CENTER + RIGHT). If you are wondering what are those jumpers for, they make sure you connect the GND to a ground plate.

6) With a multimeter, check if you have continuity between the MSX Z80 pin 11(+5V) and the Tang Nano pin 11. Then check the MSX Z80 pin 29 (GND) and the Tang Nano pin 29. If you don't STOP and check the procedure again.
Check if you got the jumpers set correctly by checking for continuity between the ground/mechanical anchor point of the ZIFF and the MSX ground.

7) Check if the A+ and A- or B+ and B- (again, depending on your instalation) are showing continuity to the +5V and -GND of your MSX Machine. I highly recomend that you connect these pads to provide power to the Tang Nano instead of relying on the flex cable and ZIFF connector.

If everything is connected correctly, your Goauld should boot just fine.


**PCB BEING USED AS THE 3.58MHz CLOCK GENERATOR**

1) VDP PIN 1 MUST BE CONNECTED TO A
2) INSTALL THE 10K RESISTOR AND A ECS-8FMX-035-TR 3.58MHz OSCILATOR (DIGIKEY-MOUSER)
3) CLOSE JP1 (CENTER+RIGHT)
4) IGNORE JP3
5) CLOSE JP2 ACCORDING TO THE ORIGINAL VDP ON YOUR MSX MACHINE



 
