# 3-axis-floor-joystick
This is a design based on the Akaki pipechair-cockpit in form factor, but with a total design of the moving assemblies to address issues with stiffness, tolerances and ease of assembly. Apart from 3D printed components, the system uses 16mm aluminium tube for its structure and axles, press-fit plain bearings, and AS5600 rotary encoders for all axes.
All attachment is either by press fit or using M3 and M4 heat-set inserts and screws. I have designed as much as possible to minimise support and make assembly straightforward.

**Rudder assembly:**
I used a clean-sheet design which dispensed with Akaki's transverse axle pedals. I found the angle of the pedals uncomfortably steep and too closely spaced; the pulley system introduced a lot of slop, as did the loose clearance and lack of bearing material around the axle. 
I saw this design as trying to imitate a more expensive sliding pedal assembly, but ultimately introduced more problems than it solved. The alternative I came up with is essentially a bicycle handlebar and stem; after some experimentation I settled on a neat 45 degree axis of rotation, which tracks decently with the natural arc of motion made by the ball of the foot when seated. As with all rotating components in this design, the axle is borne by plain bearings pressed into in the fixed assembly. The length of the pedal bars can be adjusted to the individual, as can the length of the frame. A pair of compression springs provide centering.

**Joystick assembly:**
The nested-axle design is nothing special and follows Akaki's design in approximate form, albeit with a much stiffer construction to handle greater spring forces and avoid flexing in the frame under brisk usage. The X axle is made from the standard 16mm tube and has an 8mm threaded rod through a cross hole (can be attached with hot glue, or you can tap the hole) for the Y axis, both of course riding on plain bearings. Six extension springs provide centering force. The joystick shaft is again 16mm tube and is secured with the same screws that clamp the halves of the joystick carriage together. 

**Control system:**
The joystick uses inexpensive AS5600 encoder boards to measure the angle of each axis, with a magnet fixed to the end of each axle. These are connected to an Arduino (I used a Pro Micro) using the softwarewire library to control three separate I2C devices. I soldered a daughterboard to the back of the Arduino connecting all six I2C pins to VCC with six 3.3kOhm resistors, since the impedance of the built in resistors is too high for fast polling (I suppose - I knew nothing about programming an Arduino until I started using AI to make this thing work). The Joystick library creates an HID device which is identified as a joystick by your sim. The required soldering is not too complex but poor connections can cause major headaches, so prep well.

**Attachment:**
The mounting bracket I designed is to fit a simple metal folding chair by clamping onto its crossbar. You will probably need to design something to fit whatever chair is available to you, or a way to mount it directly to the floor such as with magnets, screws or weights. 
