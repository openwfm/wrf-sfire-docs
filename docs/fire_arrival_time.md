# Fire Arrival Time

The fire arrival time is used to represent model state in data assimilation and start from remote sensing data. 
The fire arrival time, measured in seconds since the start of the simulation, is stored in variable `TIGN_G`, which is output in wrfout files. The fire arrival time
a diagnostic variable, constructed by the fire propagation algorithm within the fire region only
as a byproduct of the level set method. Outside the fire region it is normally set to a constant by the 
timestep value `dt` larger than the time now.

## Extending Fire Arrival Time into the Future



