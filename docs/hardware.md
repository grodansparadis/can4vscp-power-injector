
## Most current information

You can find the most current information about the Accra module at it's repository <https://github.com/grodansparadis/can4vscp-accra> and in the documentation at 
<https://grodansparadis.github.io/can4vscp-accra>. In the repository you can
also find links to the latest firmware, drivers and schematics etc for
its use. You can find links to where you can buy ready made modules here.

## The raw facts

| Parameter                     | Value         |
| ----------------------------- | ------------- |
| Current hardware reversion    | A             |
| Current firmware version      | 1.0.0         |
| Supply voltage                | \+9 - +28 VDC |
| PCB Size                      | 42mm x 72mm   |
| Power requirements            | 0.1W          |
| Communication: CAN4VSCP (CAN) | 125 kbps      |
| Max frequency channel 0/1     | 25KHz         |
| Max frequency channel 2/3     | 10KHz         |

## Schematics

![accra_sch_rev_a.png](./images/accra_sch_rev_a.png)

Schematics: Rev A (click picture to enlarge)

## Board components

![accra_brd_rev_a.png](./images/accra_brd_rev_a.png)

## Connectors

### Terminal block

![accra10_pinout.png](./images/accra10_pinout.png)

| Pin | Description     |
| --- | --------------- |
| 1   | Counter 0 input |
| 2   | GND             |
| 3   | \+5V            |
| 4   | Counter 1 input |
| 5   | GND             |
| 6   | \+5V            |
| 7   | Counter 2 input |
| 8   | GND             |
| 9   | \+5V            |
| 10  | Counter 3 input |
| 11  | GND             |
| 12  | \+5V            |

![accra_components.png](./images/accra_components.png)

### Pull up's

| pair | Description                           |
| ---- | ------------------------------------- |
| 1-2  | Enable 10K pullup to 5V for channel 0 |
| 3-4  | Enable 10K pullup to 5V for channel 1 |
| 5-6  | Enable 10K pullup to 5V for channel 2 |
| 7-0  | Enable 10K pullup to 5V for channel 3 |

### RJ-XX pin-out

The unit is powered over the CAN4VSCP bus. The CAN4VSCP normally uses
CAT5 or better twisted pair cable. You can use other cables if you
which. The important thing is that the CANH and CANL signals uses a
twisted cable. For connectors you can use RJ10, RJ11, RJ12 or the most
common RJ45 connectors.

Recommended connector is RJ-34/RJ-12 or RJ-11 with pin out as in this
table.

| Pin   | Use        | RJ-11 | RJ-12 | RJ-45 | Patch Cable wire color T568B |
| ----- | ---------- | ----- | ----- | ----- | ---------------------------- |
| 1     | \+9-28V DC |       |       | RJ-45 | Orange/White                 |
| 2 1   | \+9-28V DC |       | RJ-12 | RJ-45 | Orange                       |
| 3 2 1 | \+9-28V DC | RJ-11 | RJ-12 | RJ-45 | Green/White                  |
| 4 3 2 | CANH       | RJ-11 | RJ-12 | RJ-45 | Blue                         |
| 5 4 3 | CANL       | RJ-11 | RJ-12 | RJ-45 | Blue/White                   |
| 6 5 4 | GND        | RJ-11 | RJ-12 | RJ-45 | Green                        |
| 7 6   | GND        |       | RJ-12 | RJ-45 | Brown/White                  |
| 8     | GND        |       |       | RJ-45 | Brown                        |

---

![RJ-11/12/45 pin-out](./images/rj45.jpg) 


**RJ-11/12/45 pin-out**

:\!: Always use a pair of twisted wires for CANH/CANL for best noise
immunity. If the EIA/TIA 56B standard is used this condition will be
satisfied. This is good as most Ethernet networks already is wired this
way.

### Inter module connector

The inter module connector can be used to connect modules that are
physically close to each other together in an easy way. Remember that
the minimum length of a connection cable is 30 cm.

| Pin | Description             |
| --- | ----------------------- |
| 1   | Power from CAN4VSCP bus |
| 2   | CANH                    |
| 3   | CANL                    |
| 4   | GND                     |

  

![](./images/odessa_inter_module_connector.png)

### PIC programming Connector

| pin | Description                               |
| --- | ----------------------------------------- |
| 1   | Reset                                     |
| 2   | VCC                                       |
| 3   | GND                                       |
| 4   | PGD (RX of second serial port is here to) |
| 5   | PGC (TX of second serial port is here to) |
| 6   | LWPGM                                     |

  

![](./images/odessa_programming_connector.png)

### Functionality of the status LED

The LED is used to indicate the status of the module. It will light
steady when the firmware is running and will blink when the module is in
the nickname discovery process.

| LED      | Description  |
| -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Steady   | No error. Firmware running.    |
| Blinking | Module is going through the [nickname discovery process](http://www.vscp.org/docs/vscpspec/doku.php?id=vscp_level_i_specifics#address_or_nickname_assignment_for_level_i_nodes). |

### CAN

CAN4VSCP is a CAN based bus running at 125 kbps with the addition of DC
power. If you are interested in how CAN works you have a pretty good
intro [here](http://www.eeherald.com/section/design-guide/esmod9.html).

CAN is known to be robust and is there for used in vehicles and in the
industry.

  
[filename](./bottom-copyright.md ':include')
