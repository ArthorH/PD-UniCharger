![rect14220](https://github.com/user-attachments/assets/195a6d44-668b-4166-9880-3fbaf2f6ae87)

# Universal Type C charger for every battery type !

![obraz](https://github.com/user-attachments/assets/f3a32b18-92d7-44ed-8ba4-15254656f476)

## Key technologies:
 <img align="center" height="70" src="https://github.com/user-attachments/assets/21632584-becb-4529-b696-acb84c8190e9">&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;
---
# Features
- CC CV regulation
- Multiple settings
- USB C power delivery 20v
- Reverse polarity battery protection
---
# BLOCK DIAGRAM
![Untitled Diagram(3) drawio(1)](https://github.com/user-attachments/assets/3f42a0f8-0145-4837-afa8-1602aae12039)


# How it works:
## IP2721
IP2721 negotiates voltage set by J2 (short 20v open 15v) and outputs it to VBUS_PD

<p float="left">
  <img src="https://github.com/user-attachments/assets/8ebe29a4-e533-4ae5-b07a-94d76b96a368" width="300" />
  <img src="https://github.com/user-attachments/assets/75666e4f-0027-4aa0-863f-b66048ef49ce" width="500" /> 
</p>


## CC CV Stepdown
Typycal LM358 based CC CV regulation circuit
<p float="left">
  <img src="https://github.com/user-attachments/assets/a8ead8d4-49f1-4695-b69c-f5615e64859f" width="300" />
  <img src="https://github.com/user-attachments/assets/3b3a86e0-85a6-4f0e-87b1-5a8795c68d1e" width="500" /> 
</p>

### CC CV in operation
CC            |  CV
:-------------------------:|:-------------------------:
<img src="https://github.com/user-attachments/assets/5fb7d305-3f83-43fe-85e3-ac79fe420d42" width="400" />  |  <img src="https://github.com/user-attachments/assets/162c5405-b264-4f6b-a696-758c7b72af8a" width="400" /> 


## Battery reverse polarity protection 
Battery protection circuit works as SR latch with one of latching elements being P-MOS that outputs voltage to battery.
One downside to using this schematic is that charger needs to be powered down in order to "delatch" protection circuit, otherwise it may not work if battery had been disconected and reconnected again. This issue will be fixed in upcomming REV-B. 
<p float="left">
  <img src="https://github.com/user-attachments/assets/03952ef4-986d-4f59-8f45-b673f1dcc226" width="300" />
  <img src="https://github.com/user-attachments/assets/7a46a873-bafb-4495-bc38-73dc94930a46" width="500" /> 
</p>


### How it works
#### Phase 1
Power on state. Circuit is delatched. 

![Ukł_zabiezpieczający_OFF](https://github.com/user-attachments/assets/75ee5c3e-6b12-4ae8-b927-73fd339d30a3)

#### Phase 2
Connected battery starts to turn on transistor that turns on photocoupler. Circuit latches and starts charging battery, given it can provide 20ma of current and it sits above 1.5v.

![Ukł_zabiezpieczający_ON](https://github.com/user-attachments/assets/024f4715-7622-4d8c-913a-bfb8d1188115)

## Usage
Intended use is keychain charger to charge for example car battery form powerbank that is capable of PD output.

![obraz](https://github.com/user-attachments/assets/99aec52b-fe09-4321-bbdc-29edf8ee4b4a)

It is advantageous to carry a portable charging board in a vehicle or backpack as a contingency, even though its charging efficiency may not be optimal.

# License 
CERN-OHL-P
(CERN Open Hardware Licence Version 2 - Permissive)
