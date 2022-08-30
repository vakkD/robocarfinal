### Files
[1] [Car Design](https://raw.githubusercontent.com/vakkD/robocarfinal/main/cardesign.jpeg)<br>
[2] [Gearbox Plan/Design](https://raw.githubusercontent.com/vakkD/robocarfinal/main/grearboxplan_design.jpeg)<br>
[3] [Design Cards](https://raw.githubusercontent.com/vakkD/robocarfinal/main/storycard_components.jpeg)<br>
[4] [Gearbox V2 Design](https://raw.githubusercontent.com/vakkD/robocarfinal/main/gearboxv2%20compact_design.jpeg)<br>
[5] [Gearbox V1 Running](gearboxv1%20angleview_complete.mkv)<br>
[6] [Gearbox V1 Blender File](gearboxv1.blend)<br>
[7] [Gearbox V1 Calculations](gearboxv1%20calculations.txt)<br>
[8] [Car Shell Design V1](carpototyperobotics.blend)<br>
[9] [Box and Arrows Design](https://raw.githubusercontent.com/vakkD/robocarfinal/main/robocar_box_arrow.jpg)

### Links
[10] [Gear Generator (with my gearv1 design)](https://geargenerator.com/#200,200,100,6,0,0,341.40000000000146,4,1,12,3,4,20,0,0,0,0,0,0,1,6,1.5,4,20,0,0,0,0,0,0,0,24,6,4,20,-35,0,0,0,0,2,1,6,1.5,4,20,-35,0,0,0,0,0,1,3,-35)<br>
[11] [Gear Ratios](https://woodgears.ca/gear/ratio.html)<br>
[12] [Gear Types](https://khkgears.net/new/gear_knowledge/the-first-step-of-mechanism-design-using-gears/know-about-gear-types-and-relations-between-the-two-shafts.html)


# Description
Our project is to create an RC car using Arduino components, using knowledge from the simple car we created the last term. We will implement systems such as gearing and motors. The intended audience of this project would be people who have an interest in RC cars and want to expand their knowledge and see how they can make them and improve upon its design. The project itself can also be used as an educational resource as the theory behind the car itself is relatively simple in terms of motor control and would allow people to have fun learning about stepper and general DC motors and how they function.

We are making an Arduino RC car. We are taking what we created last term and massively improving it. My role in this project is to design and create the steering mechanism, gearbox and differential rear wheel drive. Lewis' role is to program the motors and Elisha has control of all the circuitry.

# My Role and Idea
### Main Drive
Two motors can be used to increase the torque, using a differential for two inputs and one output, allowing two motors to power one shaft [[3.2]](https://raw.githubusercontent.com/vakkD/robocarfinal/main/storycard_components.jpeg). Or two motors spinning in the same direction, on either side of the shaft, both giving power directly to the shaft [[3.4]](https://raw.githubusercontent.com/vakkD/robocarfinal/main/storycard_components.jpeg), though two motors would be very unlikely to be needed and we will probably just use one motor. This setup of two motors would only be needed if the car ends up being very heavy.
<br><br>
### Gear System Overview
The motor power will be driven into the gearbox which will control the torque and speed depending on the terrain. The design that I have created currently only supports manual transmission (without a clutch). Meaning at the moment, shifting has to be done using an external servo motor. The gearbox is two-speed, 2:1 and 1:2 [[11]](https://woodgears.ca/gear/ratio.html), the gif below explains better how this works, but the big and small gear switch spots, from input to output. Having the small gear as input creates more torque (2:1) and the large gear as input creates more speed (1:2) [[7]](https://raw.githubusercontent.com/vakkD/robocarfinal/main/gearboxv1%20calculations.txt), this can be seen [[10]](https://geargenerator.com/#200,200,100,6,0,0,341.40000000000146,4,1,12,3,4,20,0,0,0,0,0,0,1,6,1.5,4,20,0,0,0,0,0,0,0,24,6,4,20,-35,0,0,0,0,2,1,6,1.5,4,20,-35,0,0,0,0,0,1,3,-35). This power will then feed into the drive shaft that will go into the limited slip diff and spin both the back wheels [[3.1]](https://raw.githubusercontent.com/vakkD/robocarfinal/main/storycard_components.jpeg) and [[1]](https://raw.githubusercontent.com/vakkD/robocarfinal/main/cardesign.jpeg). My box and arrows design is a better representaion of this [[9]](https://raw.githubusercontent.com/vakkD/robocarfinal/main/robocar_box_arrow.jpg), this shows the full system and how I plan to lay everything out, at the moment anyway.
<br><br>
### Turning System
Turning will work with one stepper motor (explained why in Lewis' writeup) connected to a gear at the end. This end gear will be on a gear rack [[11]](https://khkgears.net/new/gear_knowledge/the-first-step-of-mechanism-design-using-gears/know-about-gear-types-and-relations-between-the-two-shafts.html), moving the plate left and right, which then turn the wheels [[3.3]](https://raw.githubusercontent.com/vakkD/robocarfinal/main/storycard_components.jpeg). Using a gear rack like this allows us to turn the wheels itself, instead of using wheel speed. Both wheels turn on their own axis.
<br><br>
### Gearbox
My original design for the gearbox can be seen in file [[2]](https://raw.githubusercontent.com/vakkD/robocarfinal/main/grearboxplan_design.jpeg), this didn't work for many reasons so I decided to start over. Playing with gear ratios and doing lots of research, I realised that instead of trying to shift to an entire different train (trying to replicate a cars gearbox) I can just change the order. So far it is only 2-speed with an automatic-manual transmission. 

![gearboxv1 angleview_complete_compressed.gif](https://github.com/vakkD/robocarfinal/blob/main/gearboxv1%20angleview_complete_compressed.gif)
<br><sub>(the quality is bad due to attempts at reducing file size, loss-less version [[5]](https://github.com/vakkD/robocarfinal/blob/main/gearboxv1%20angleview_complete.mkv), the gear speed is not accurate on this demonstration, it is only to show the mechanism)</sub>

I have created a new, more compact design [[4]](gearboxv1%20angleview_complete.mkv), this is not worth giving a description for as it follows the same principle as V1 [[7]](gearboxv1%20calculations.txt), just has a shortened rod, condensing the entire mechanism, all other components are the same.
<br><br>
### Car Frame Design
I created a rough 3D model for the car, so that we can print it later [[8]](carpototyperobotics.blend). The wheels will fall off each side and be supported by some suspension [[1]](https://raw.githubusercontent.com/vakkD/robocarfinal/main/cardesign.jpeg).

I have gone over the design for many components a number of times, I have finalised all these mentioned here but I think there will be changes later down, especially with the gearbox.

# Project Story Cards
Must have:
- Differential Rear Wheel Drive
- Steering Mechanism

Should have:
- Manual 2-Speed Gearbox
- I2C : Remote to Car

Could have:
- Automatic Gearbox
- RC : Remote to Car
- Multispeed Gearbox
