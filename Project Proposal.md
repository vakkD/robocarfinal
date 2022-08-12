### Files
[1][Car Design](cardesign.jpeg)<br>
[2][Gearbox Plan/Design](grearboxplan_design.jpeg)<br>
[3][Story Card](storycard_components.jpeg)<br>
[4][Gearbox V2 Design](gearboxv2%20compact_design.jpeg)<br>
[5][Gearbox V1 Running](gearboxv1%20angleview_complete.mkv)<br>
[6][Gearbox V1 Blender File](gearboxv1.blend)<br>
[7][Gearbox V1 Calculations](gearboxv1%20calculations.txt)

### Links(forme)
[Gear Generator (with my gearv1 design)](https://shorturl.at/dGQU8)<br><!--https://geargenerator.com/#200,200,100,6,0,0,341.40000000000146,4,1,12,3,4,20,0,0,0,0,0,0,1,6,1.5,4,20,0,0,0,0,0,0,0,24,6,4,20,-35,0,0,0,0,2,1,6,1.5,4,20,-35,0,0,0,0,0,1,3,-35-->
[Gear Ratios](https://woodgears.ca/gear/ratio.html)<br>
[Gear Types](https://khkgears.net/new/gear_knowledge/the-first-step-of-mechanism-design-using-gears/know-about-gear-types-and-relations-between-the-two-shafts.html)


# Description
We are making an Arduino RC car. We are taking what we created last term and massively improving it. My role in this project is to design and create the steering mechanism, gearbox and differential rear wheel drive. Lewis' role is to program the motors and Elisha has control of all the circuitry.

# My Role and Idea
Two motors can be used to increase the torque, using a differential for two inputs and one output, allowing two motors to power one shaft [[3.2](storycard_components.jpeg)]. Or two motors spinning in the same direction, on either side of the shaft, both giving power directly to the shaft [[3.4](storycard_components.jpeg)], though two motors would be very unlikely to be needed. This setup of two motors would only be needed if the car ends up being very heavy (refer to diagram NUMBER?). The motor power will be driven into the gearbox which will control the torque and speed depending on the terrain. The design that I have created currently only supports manual transmission (without a clutch). The gearbox is two-speed, 2:1 and 1:2, the gif below explains better how this works, but the big and small gear switch spots, from input to output. Having the small gear as input creates more torque (2:1) and the large gear as input creates more speed (1:2), this can be seen [[!!!!!!!!!!!!!CHANGENUM]](https://shorturl.at/dGQU8). This power will then feed into the drive shaft that will go into the limited slip diff and spin both the back wheels [[3.1]](storycard_components.jpeg) and [[1]](cardesign.jpeg). Turning will work with one stepper motor (explained why in Lewis' writeup) connected to a gear at the end, going through a gear ratio of 2:1 to allow the end to spin faster, creating faster and sharper turns. This end gear will be on a gear rack, moving the plate left and right, which then turn the wheels (refer to diagram NUMBER?).

I have gone over the design for many components a number of times, I have finalised all these but I think there will be changes later down, especially with the gearbox.

My original design for the gearbox can be seen in file [[2]](grearboxplan_design.jpeg), this didn't work for many reasons so I decided to start over. Playing with gear ratios and doing lots of research, I realised that instead of trying to shift to an entire different train (trying to replicate a cars gearbox) I can just change the order. So far it is only 2-speed with an automatic-manual transmission. 

![gearboxv1 angleview_complete_compressed.gif](https://github.com/vakkD/robocarfinal/blob/main/gearboxv1%20angleview_complete_compressed.gif)
<br>(the quality is bad due to attempts at reducing file size, loss-less version [[5]](https://github.com/vakkD/robocarfinal/blob/main/gearboxv1%20angleview_complete.mkv)

I have created a new, more compact design
