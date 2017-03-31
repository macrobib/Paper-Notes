#### A Modular Parametric Architecture for the TORCS Racing Engine

- Control architecture for TORCS: gear control, low level throttle and brake control, target speed determination using TSK fuzzy controller that uses a reduced set of fuzzy rules and Oponent modifier.
- UDP based client server communication.
- Gear control - Change gears.
- Speed Module - Assign allowed speed for a given track.
- Low level Gas & Brake control module: Follow indication of desired speed gas and brake pedal.
- Steering Control : Control the car.
- Opponent modifier module: React to opponent presence, modify steering, gas & brake to adapt driving to bring about collision avoidance or overtaking.
- Steering control base don ORBEX Fuzzy coprocessor. Implements fuzzy system modelled with singeleton shapes in output.
- 3 of the 19 track sensors available are used to determine 3 specific rules: 
	- Track sensor that measures the front distance to 
    track axis.
    - Max value between track sensors at +10 degree.
    - Max value between track sensors at +20 degree.
    - Trapezoid membership function is generated : {Low, Medim, High}.
    - 7 Rules to calculate the target speed.

- Accel Braking: When reverse braking applied values set to 1, else diff between target and current speed is taken and passed through a logistic function, to determine the absolute speed.
- ABS: acceBrake - (speed - speed_wheels - 1.5)/5
- Steering angle: Weighted average of 9 track sensors.
- Seperate equation for reverse(Stuck) scenario and outsde the track scenario.
