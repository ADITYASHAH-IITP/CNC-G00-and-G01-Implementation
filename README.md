![ezgif com-gif-maker](https://user-images.githubusercontent.com/37467941/114655522-f96f0080-9d09-11eb-82fe-ba2f13adbb28.gif)   ![ezgif com-gif-maker (1)](https://user-images.githubusercontent.com/37467941/114849374-4c75b000-9dfd-11eb-8f6b-7dc8f17dea9a.gif)

# CNC-G00-and-G01-Implementation
G - Address for preparatory commands
  - This commands often tell the control what kind of motion is wanted (e.g., rapid positioning, linear feed, circular feed, fixed cycle) or what offset value to use.

G00 ( Rapid positioning )	--> On 2- or 3-axis moves, G00 (unlike G01) traditionally does not necessarily move in a single straight line between start point and endpoint. It moves each axis at its max speed until its vector quantity is achieved. A shorter vector usually finishes first (given similar axis speeds). This matters because it may yield a dog-leg or hockey-stick motion, which the programmer needs to consider, depending on what obstacles are nearby, to avoid a crash. Some machines offer interpolated rapids as a feature for ease of programming (safe to assume a straight line).

G01	( Linear interpolation) -->	The most common workhorse code for feeding during a cut. The program specs the start and endpoints, and the control automatically calculates (interpolates) the intermediate points to pass through that yield a straight line (hence "linear"). The control then calculates the angular velocities at which to turn the axis leadscrews via their servomotors or stepper motors. The computer performs thousands of calculations per second, and the motors react quickly to each input. Thus the actual toolpath of the machining takes place with the given feed rate on a path that is accurately linear to within very small limits.

![CNC G00 and G01](https://user-images.githubusercontent.com/37467941/114524466-de958100-9c62-11eb-9d6d-5859e5f33585.gif)


