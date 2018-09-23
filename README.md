# Stepper-Motor-Dividing-Head
Code to run a controller which in turn runs a stepper motor driven dividing head. 
The controller has 3 x 7 segment digit displays, driven by 3 x 4511 decoder integrated circuits.
In addition it has 4 toggle switches and a push button. The controller allows the user to first select the number of divisions (per 360 degree rotation) and then allows the user to move forward or backwards, 1, 2, 5 or 10 divisions with each push of the button depending on the selection made with the toggle switches.

The controller may be set in either of two modes using the `mode_pin` toggle switch on the controller. Regardless of which mode is chosen the remaining 3 toggle switches have the same function. The first of these (the `fwd_tog_pin` switch) determines whether a button press moves forward (by adding to the number on the display) or moves in reverse. The other two toggle switches (`tog1_pin` and `tog2_pin`) act as a pair to provide 4 possible combinations to be selected on. This selection allows an increment of 1, 2, 5 or 10 to be selected by the user.

The first mode is the 'set mode'. In this mode the number divisions which has been selected is displayed. If the button is pushed the number is incremented by an amount dependent on the other toggle switches. Any integer value from 2 up to 999 may be selected. If the increment goes past this range the number wraps around.

The second mode is the 'run mode'. In this mode the dividing head is incremented each time the button is pushed. Again the increment depends on the toggle switch selection. The display shows the division number the dividing head is currently at, starting at 0 and going up to the number n, which is one less than the number of divisions chosen in set mode. The number on the display wraps around when this range is incremented past. 
