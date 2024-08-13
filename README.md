![rect14220](https://github.com/user-attachments/assets/c31b2a06-c299-41f1-85e2-4e734374da6b)
# Universal Type C charger for every battery type !





<p align="center">
  <img src="https://github.com/user-attachments/assets/ab841e63-6dea-45bb-a0b9-0a02dccfb278" width="500" height="400">

</p>


---
# Features
- CC CV regulation
- Multiple settings
- USB C power delivery 20v
- Reverse polarity battery protection
---
# BLOCK DIAGRAM
![Diagram](https://github.com/user-attachments/assets/73b9adbd-b84a-4058-acd4-38fc4216278a)

# How it works:
## IP2721
IP2721 negotiates voltage set by J2 (short 20v open 15v) and outputs it to VBUS_PD

<p float="left">
  <img src="https://github.com/user-attachments/assets/dbf40558-98c7-421c-9e88-e705fd616f41" width="300" />
  <img src="https://github.com/user-attachments/assets/41ef5dbd-3547-4ded-a643-c4d643367bb6" width="600" /> 
</p>


## CC CV Stepdown
Typycal LM358 based CC CV regulation circuit
<p float="left">
  <img src="https://github.com/user-attachments/assets/e0b2b6eb-e4b7-404b-a2d0-819a9ba96c03" width="300" />
  <img src="https://github.com/user-attachments/assets/eb8d84c9-d5d9-464f-b1db-28ef488ed5df" width="600" /> 
</p>

### CC CV in operation
CC            |  CV
:-------------------------:|:-------------------------:
<img src="https://github.com/user-attachments/assets/52f94ccd-6d2e-4de8-b153-cb9145421fc8" width="400" />  |  <img src="https://github.com/user-attachments/assets/fb550654-70b6-4203-aada-ebab0d155826" width="400" /> 

## Battery reverse polarity protection 
Battery protection circuit works as SR latch with one of latching elements being P-MOS that outputs voltage to battery.
One downside to using this schematic is that charger needs to be powered down in order to "delatch" protection circuit, otherwise it may not work if battery had been disconected and reconnected again. This issue will be fixed in upcomming REV-B. 
<p float="left">
  <img src="https://github.com/user-attachments/assets/7e271042-7818-400e-84fb-f9e1f21c285d" width="300" />
  <img src="https://github.com/user-attachments/assets/feb45b0c-082d-4017-b996-f628a89ffb4c" width="600" /> 
</p>

### How it works
#### Phase 1
Power on state. Circuit is delatched. 

![Ukł_zabiezpieczający_OFF](https://github.com/user-attachments/assets/c310f47a-c93b-4e58-9d16-0d12ae34bb83)

#### Phase 2
Connected battery starts to turn on transistor that turns on photocoupler. Circuit latches and starts charging battery, given it can provide 20ma of current and it sits above 1.5v.

![Ukł_zabiezpieczający_ON](https://github.com/user-attachments/assets/254022d0-ead3-40fb-8070-797526705ee5)

## Usage
Intended use is keychain charger to charge for example car battery form powerbank that is capable of PD output.
<img src="https://github.com/user-attachments/assets/21cf65ee-64dc-4c46-9eae-e253a5655d08" width="300" />

Or li-ion / li-pol cell (using different settings) for various use cases.

<img src="https://github.com/user-attachments/assets/b372cdb2-a3e2-4344-b34e-be1fe2ebd6a9" width="300" />

It is definitely better to have one of those boards lying arround in car or in backpack than not even tho it does not offer best charging performance. 

# License 
CERN-OHL-P
(CERN Open Hardware Licence Version 2 - Permissive)
