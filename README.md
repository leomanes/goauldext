# 40-Pin Extension for MSX Goa'uld + 3.58 MHz Clock Generator / VDP Replacement

The MSX Goa'uld does not need the VDP itself. It only needs the VDP clock.

This PCB can be used in three different places:

- Z80 socket
- Tang Nano 20K side
- VDP socket, when used as a 3.58 MHz clock generator

<img width="1583" height="1078" alt="image" src="https://github.com/user-attachments/assets/4daf8787-346d-4156-8ee5-1158df9f6041" />

This extension allows the MSX Goa'uld, based on the Tang Nano 20K, to be installed away from the Z80 socket. The same PCB can also be installed in the VDP socket and configured to generate the required 3.58 MHz clock.

The image below shows the PCB in three configurations:

- **Yellow box, left:** connected to the Tang Nano 20K
- **Yellow box, right:** installed in the Z80 socket
- **Red box:** installed in place of the VDP to generate the 3.58 MHz clock

---

## Configuring the Extension

> [!CAUTION]
> Incorrect configuration may damage your MSX computer and/or the Tang Nano.

<img width="744" height="1675" alt="image" src="https://github.com/user-attachments/assets/c538c27b-b24f-47c0-a5d6-db4733f36fd7" />

### Important Notes

#### Z80 Socket PCB

The PCB installed in the Z80 socket must always have the 40-pin ZIF connector soldered to the **top** of the board.

#### Tang Nano PCB

The PCB that holds the Tang Nano 20K must have its socket installed on the **underside** of the board.

#### Cable Length

The maximum recommended length for the 40-pin flex cable is **20 cm**.

A 30 cm cable has been reported to work, but feedback on this setup is limited.

#### Connectors

This extension only requires ZIF connectors.

---

## Installation Steps

### 1. Orient the Z80 PCB

Plug the PCB into the Z80 socket, making sure the ZIF connector is on top.

Orient the PCB so the flex cable exits in the direction you prefer.

---

### 2. Identify Pin 1

Locate Pin 1 of the Z80.

Check which letter on the PCB Pin 1 is connected to:

- **A**
- **B**

---

### 3. Align the Tang Nano PCB

Plug in or solder your Tang Nano 20K, making sure its Pin 1 matches the same letter found in the previous step.

- If Z80 Pin 1 is on **A**, Tang Nano Pin 1 must also be on **A**.
- If Z80 Pin 1 is on **B**, Tang Nano Pin 1 must also be on **B**.

> [!NOTE]
> If the HDMI port is not facing your preferred direction, you may need to use an HDMI flex extension.

---

### 4. Set the Jumpers

Once you know whether your installation uses side **A** or side **B**, configure the solder jumpers.

#### JP1

Close **JP1** on the **GLD side**:

- Close **LEFT + CENTER**

#### JP3

Close **JP3** according to your installation letter:

- **A:** close **LEFT + CENTER**
- **B:** close **CENTER + RIGHT**

These jumpers ensure that the ZIF mechanical anchor and ground are correctly connected to the ground plane.

---

## Testing

Before powering the system, perform the following checks with a multimeter.

### Continuity Check

Verify continuity between:

- MSX Z80 Pin 11 `+5V` and Tang Nano Pin 11
- MSX Z80 Pin 29 `GND` and Tang Nano Pin 29

### Ground Check

Verify continuity between the ZIF mechanical anchor point and MSX ground.

> [!WARNING]
> If any of these checks fail, stop immediately and re-check your installation.

### Power Pads

Check that the correct power pads show continuity to the MSX power rails.

Depending on your installation, verify either:

- `A+` and `A-`
- `B+` and `B-`

These pads should have continuity to the MSX `+5V` and `GND`.

> [!TIP]
> It is highly recommended to connect these pads directly to power the Tang Nano, instead of relying only on the flex cable and ZIF connector.

If everything is configured correctly, the Goa'uld should boot successfully.

---

# Using the PCB as a 3.58 MHz Clock Generator

This configuration is optional and is used when replacing the VDP clock source.

## Alignment

VDP Pin 1 must be connected to **A**.

## Required Components

Install the following components:

- `10 kΩ` resistor
- `ECS-8FMX-035-TR` 3.58 MHz oscillator

The oscillator is available from suppliers such as DigiKey and Mouser.

## Jumper Settings

Configure the jumpers as follows:

### JP1

Close:

- **CENTER + RIGHT**

### JP3

Ignore JP3.

### JP2

Close JP2 according to the original VDP type used in your specific MSX machine.
