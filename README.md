# 40-Pin Extension for MSX Goa'uld / 3.58MHz Clock Gen

<img width="1583" height="1078" alt="image" src="https://github.com/user-attachments/assets/46ef58d3-06aa-42e3-b49e-743d15e26327" />

This extension allows the **MSX Goa'uld (Tang Nano 20K)** to be installed away from the Z80 socket. The PCB can also be installed in the VDP socket and configured to generate a 3.58MHz clock.

The images below show the PCB in three configurations: 
* **Yellow box (left):** Connected to the Tang Nano 20K.
* **Yellow box (right):** Installed in the Z80 socket.
* **Red box:** Replacing the VDP to generate the 3.58MHz clock.

## Configuring the Extension: Important Notes

> [!CAUTION]
> **ATTENTION:** Incorrect configuration may damage your MSX machine and/or the Tang Nano.

> <img width="744" height="1675" alt="image" src="https://github.com/user-attachments/assets/a2e3fd41-0a71-4e50-96ca-8776aa0ea3ff" />

* **Z80 Socket PCB:** The PCB installed in the Z80 socket must always have the **40-pin ZIF connector** soldered to the **TOP** of the board.
* **Tang Nano PCB:** The PCB that holds the Tang Nano 20K must have its socket installed on the **UNDERSIDE** of the board.
* **Cable Length:** The maximum recommended length for the 40-pin flex cable is **20cm**. While 30cm has been reported to work, it may cause system instability.
* **Connectors:** The extension only requires ZIF connectors.

## Installation Steps

1.  **Orient the Z80 PCB**
    Plug the PCB into the Z80 socket (ensure the ZIF is on top) so that the flex cable runs in your desired direction.

2.  **Identify Pin 1**
    Locate Pin 1 of your Z80. Determine which letter on the PCB it is connected to: **A or B**.

3.  **Align the Tang Nano**
    Plug or solder your Tang Nano 20K, ensuring its Pin 1 aligns with the same letter found in the previous step.
    * If Z80 Pin 1 is on **A** → Tang Nano Pin 1 must be on **A**.
    * If Z80 Pin 1 is on **B** → Tang Nano Pin 1 must be on **B**.
    * *Note: If the HDMI port is not facing your preferred direction, you may need an HDMI flex extension.*

4.  **Set Jumpers**
    * Once you know your letter, close the **JP1 (LEFT + CENTER)** solder jumper (**GLD side**).
    * Close the **JP3** solder jumper based on your installation letter:
        * **A:** Close LEFT + CENTER.
        * **B:** Close CENTER + RIGHT.
    * *These jumpers ensure the ZIF mechanical anchor/ground connects correctly to the ground plane.*

## Testing and Power

* **Continuity Check:** Using a multimeter, verify continuity between **MSX Z80 Pin 11 (+5V)** and **Tang Nano Pin 11**. Then check **MSX Z80 Pin 29 (GND)** and **Tang Nano Pin 29**.
* **Ground Check:** Verify continuity between the ZIF mechanical anchor point and the MSX ground. **If any of these checks fail, STOP and re-verify your steps.**
* **Power Pads:** Check that the **A+/A-** or **B+/B-** pads (depending on your install) show continuity to the +5V and GND of the MSX. 
    * *Recommendation:* It is highly recommended to connect these pads directly to provide power to the Tang Nano rather than relying solely on the flex cable and ZIF connector.

If everything is correct, your Goa'uld should boot successfully.

## Using the PCB as a 3.58MHz Clock Generator

* **Alignment:** VDP Pin 1 must be connected to **A**.
* **Components:** Install a `10k` resistor and an `ECS-8FMX-035-TR` 3.58MHz oscillator (available at DigiKey/Mouser).
* **Jumpers:**
    * Close **JP1 (CENTER + RIGHT)**.
    * Ignore **JP3**.
    * Close **JP2** according to the original VDP type used in your specific MSX machine.


