# lunco-matrix
Matrix is a set of Linux drivers that fakes sensor data for robot from LunCo sim world

## Idea

Your Linux-based flatsat will feel data from running LunCo sim as real. 

There is almost no difference in configuration between flight and sim modes.

## Workflow

1. You create a digital twin of you robot in LunCo: HW used
2. LunCo simulates low-level protocols: PWM, RS-422, etc
3. You install Matrix on your Linux-based flatsat e.g. RPI
4. Matrix creates virtual interfaces based on LunCo configuration and fills these interfaces with realtime data from LunCo sim
5. Matrix uses UDP + CCSDS to communicate with LunCo server
6. Matrix precisely imitates data from sensors utilizing it's internal model. E.g. LunCo sends updates with Accelerometer data at a rate 10 Hz, FlatSat utilizes Accelerometer at a rate of 100Hz. In that case Matrix will provide FlatSat with data at 100Hz rate based on LunCo sim and model of Accelerometer data

## Applications
0. **Cooperative missions**. 

    1. Several parties in their MCC run their flatsat and train together in virtual environment.

1. SW testing
2. Algorithm tuning
3. AI training base
