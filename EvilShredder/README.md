## What is the EvilShredder?

One day an enduser received a letter explaining how **Evil Company** specializes in document destruction wants to setup a meeting to become a vendor, further down in the letter, the company explains that they care about their customer's safety so much that they are sending a paper shredder along as a free gift. The enduser smiles at their new shredder still fresh in the box. They setup it up and away they go shredding happily.
## How is it evil? 

Inside of the shredder is the following components. 

- Raspberry PI 4 
- 4G Cellular Radio 
- Pi Camera(s)

Every time a user shreds a document, the camera module is activated by the switch that powers the shredder motors and stores a video of the camera's output to the Rasp PI SD card.  Once the video is on the SD Card, exfiltrating the data over the cellular radio becomes trivial. Since the cellular radio is the primary method of controlling the implant, an attacker could easily attempt to attack any Wireless networks nearby and if successful could then scan / attack the network.   
   


## Why a Shredder? 
 
A shredder was chosen for several reasons: 

- No one expects a shredder to be malicious! 
- Plenty of Negative Space. 
- Always powered (AC).
- Every office has them. 


## Why a camera? 

An implant that focuses on just attacking the network would be easy to implement, but primary function of a shredder is to destroy sensitive / confidential information. Implanting a device in a shredder and not attempting to harvest this information would be like buying a Ferrari and driving the speed limit. 



## Information Gathered so far


![BottomView](/images/BottomView.jpg)

In this image, we see the bottom of the shredder module, all of them are standard Philips head screws with nothing to indicate that the device was tampered with.


Once we remove the eight screws holding the backplate on, we see the following components.

![Internal-View](/images/InternalView.jpg)


There is so much internal space available that an encased Raspberry Pi 4 could be used instead of the originally planned Pi Zero WH.

![Raspberry Pi](/images/CircuitRasp.jpg)


The next interesting part of this setup is the top plate of document feeder, this is where the enduser would input the documents. To keep the device as safe as possible, the manufactures use a very small grove that can fit paper but not much else. This is perfect for concealing a camera or camera array away from the user's line of sight.

![Top Feeder](/images/FeederTop.jpg)


On the bottom of the document feeder is already reinforced with ribs that offer the perfect place to anchor the camera / cameras. 

![Bottom Feeder] (/images/FeederBottom.jpg)

To save power / processing, we need a mechanism that can trigger the camera to activate when a target input a piece of paper.  The AutoStart switch is the perfect place to capture the signal.

![Switch] (/images/Switch.jpg)
 
## Challenges  ( So Far )

- Whenever you deal with AC power, you need to have a professional looking over your shoulder. AC can be lethal. 
- Controlling one Camera is easy, if you must create a camera array, a question of Rasp PI data bus being able to support that much bandwidth with any quickness comes into play.
- Low light inside of Feeder area might require using an IR camera. 
- Camera focal length might be an issue. 
- Pi compatible cellular radio + data plan is one step above highway robbery.


## Proof of Concept 

Currently waiting on electrical Engineer to accept a trade of Guinness to help keep me from burning my house down. For the other components, I am waiting for them to arrive :(
