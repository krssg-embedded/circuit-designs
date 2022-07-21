# Circuit Design
This repo contains all the schematics and pcb layout designs relevant to the SSL bot.
There are three imporatant circuits in the bot:
1. Main Board
2. Kicker Circuit
3. Motor Driver

### Main Board

### Kicker Circuit
The kicker we use works on the principle of a solenoid.
The straight kicker is powered by two 250V 2200uF capacitors, which can be charged by a step-up converter to 200V each.
The kicker board constitutes of a charging and a discharging circuit. The FPGA on the main circuit is controlling the circuit. The board receives charge trigger and kicking level from the main circuit, charging the capacitor bank of 4400uF to 250V using flyback topology.
The charging circuit is based on LT3750, a flyback converter. It consists of a different resistor which can be used to change various output parameters like charging current. The CHARGE pin one the IC gives full control of the LT3750 to the user and the DONE pin indicates when the capacitor has reached its programmed value, and the part has stopped charging.
The capacitor is charged to its limit by using a boost convertor that steps up the voltage from the the 12V battery. The kicker is operated through a switch which disconnects the charging circuit and allows the charge from the capacitor to flow through the solenoid. 
As the kicker is made of a magnetic material as soon as the current flows the coil tries to bring as much of the kicker inside itself as possible. This is what generates the tremendous kicking force required to kick the ball.

### Motor Driver
MOTOR DRIVER
In motor driver, I learnt how to make a commutation table.
I learnt in detail about the internal circuitry of the driver. I read about power MOSFETs and their advantages. We were taught the problems that we currently face in running our BLDCs. I learnt to place the components on the PCB and solder them properly. I also read about the gate driver IC we use and how it helps us in switching the states of the mosfets.
I read about the various methods of sensing commutation which includes using Hall sensors, using encoders and finally back-EMF calculations. The methods of control like trapezoidal, sinusoidal and field oriented control. The current sensor IC ACS2590 was also introduced. 
The main takeaway was that there are problems in the circuitry that we use and many things can be improved like we can implement sinusoidal current by applying variable PWM or make the commutation smoother by adjusting the rise and fall time of the voltages at the gates.
