A tiny new CA device has all the capabilities of a Universal Constructor, namely that it can self-replicate, and if extended can recreate any pattern of cells, yet fits in an 8x27 rectangle. This post describes the pattern and its associated rule in detail.

![Partial Construction of Child Device](/assets/images/2023-10-14/image3.png "Partial Construction of Child Device")

### Background
If you are not familiar with Universal Constructors, I recommend you read this first: 

[Von Neumann Universal Constructor]( https://en.wikipedia.org/wiki/Von_Neumann_universal_constructor)

Also, some background on Wireworld would be useful so check out: 

[WireWorld](https://en.wikipedia.org/wiki/Wireworld)

### The Device

Traditionally, a Universal Constructor is formed from two parts, a tape, which stores genetic information, and a machine, which interprets the information and constructs the next generation. Together these parts look like this:

![The Device](/assets/images/2023-10-14/image2.png "The Device")

As you can see from the diagrams, and imagining they are connected together by a length of wire 800 cells long, the five loops and the connecting wires form one continuous loop.

### Anatomy 
The device looks like this:

![Anatomy](/assets/images/2023-10-14/image1.png "Anatomy")

| Part | Description | 
| Transmission Arm | Sends data from the parent to the child |
| Construction Arm | Constructs the Child |
| Replicator | Splits data from the loop and passes to the Construction Arm and Transmission Arm |
| Tape Loops | Store genetic information |
| Reception Arm | Receives genetic information from parent |
| Start/Stop Gate | Controls flow of information from parent to child |
| XOR Gate | Allows information to flow from parent to child and within the machine | 

### Phases of Operation

Operation proceeds in two phases, which are a collaboration between parent and new child.

1. Construction. The Parent starts to create the loop, and the machine that will form the Child. Construction takes four steps: 
a. Construct the machine and the left side of the loops. 
b. Construct the right side of the loops. 
c. Insert Auto-Expand Photons at the center of each of the loop strands. Auto-Expand Photons then splay out and connect the loops together. Crucially, since Auto-Expand photons are fast compared with the Retract Photons running in the construction arm at this point, step c naturally completes before step d.
d. Create a cell which joins the Transmission Arm of the Parent with the Reception Arm of the Child.

2. Transmission. The Start/Stop gate starts in the Start State, while the Reception Arm is missing one cell. When the Start/Stop gate detects a Shadow Start Photon, it bridges the gap with a cell, and transitions into the Stop state. Data starts to flow until the Start/Stop gate detects a Shadow Stop Photon, at which point it breaks the connection again, while remaining in the Stop State. In this way exactly one copy of the genetic data is copied to the child.

After this, the cycle repeats with the Child constructing the grand-child and so on down the line.

### States

The CA Rule uses 19 states which are outlined in the following table:

| Number | Name | Color | Notes |
| 0 | Background | Black |  |  
| 1 | Photon Tail | White | | 
| 2 | Material | Orange | Material used for wires |
| 3 | Wire | Green | Material used for the construction arm |
| 4 | Action Extend | Red | Extend the construction arm by one cell either right or up |
| 5 | Action Retract | Yellow | Retract the construction arm by one cell | 
| 6 | Action Deposit | Light Blue | Deposit a cell at the end of the construction arm. First time: deposit Orange Material. Second time: change to Gate Start. Third time: change to Auto-expander. Note that although it's not the rarest, Auto-expander has to be last in this order since once you create it, it starts to work, and is gone! |
| 7 | Action Left | Purple | Build one cell on the left of the head of the construction arm. |
| 8 | Shadow Photon Tail | Grey | |
| 9 | Stop Marker | Blue | Indicates that the Construction Arm is done working and will not allow any more Action Photons to pass |
| 10 | Shadow Extend | Dark Red | Shadow of Action Extend (Shadow photons run on Material and are transformed into Action Photons when they are transferred onto the construction arm) |
| 11 | Shadow Retract | Dark Yellow | Shadow of Action Retract |
| 12 | Shadow Deposit | Dark Blue | Shadow of Action Deposit |
| 13 | Shadow Left | Dark Purple | Shadow of Action Left |
| 14 | Shadow Action Start | Red | Indicates the start of the sequence of instructions. Interacts with and "opens" the Start/Stop gate. |
| 15 | Shadow Action Stop | Yellow | Indicates the end of the sequence of instructions. Interacts with and "closes" the Start/Stop gate. |
| 16 | Auto-Expander | Purple | Upon creation, moves to the left and right at light-speed leaving behind a trail of Material. Stops when it encounters something other than Background. |
| 17 | Gate Start | Green | Indicates that the Gate is ready to be opened | 
| 18 | Gate Stop | Red | Indicates that the Gate is ready to be closed | 


### Container Problem
Traditionally, the loop needs to be constructed using some other method than simply following instructions, for the following reason. The loop has two strands, each n cells long. This means the maximum instructions we can store is 2n/3. However to construct the tape we need 2n instructions. We solve this problem in the following way: The loop is folded into 10 strands, each of length n. The method of construction ( using auto-expanders ) means that we still need approximately 2n instructions to generate the tape, while the number of instructions we can store has risen to 10n/3. Thus the problem is solved. Constructing the tape using instructions only, further simplifies the device.


### Wireworld Variant
A few words about the wireworld variant used. Wireworld itself could have been used as the model for transmission of photons along wires. However the rules for building Wireworld are complex, and have to be duplicated for each type of photon. I have in the past used a variant of Wireworld called Wireworld1 which has simpler rules. Specifically, while in Wireworld a wire becomes an electron head if 1 or 2 electron heads are neighbors, in Wireworld1 a wire becomes an electron head if exactly 1 electron head is a neighbor. Wireworld1 supports logic gates ( a different primitive set, but still universal ), and computation. The simplest gate in Wireworld1 is the XOR gate - that's why I used it in the machine - because it's simple to construct. The way transmission works ensures that there are never photons on both inputs of the gate, and so in effect this XOR gate works just like an OR gate ( which is harder to build in Wireworld1 ).


### Demo

Links to Youtube videos of the CA in action: 

[Universal Constructor](https://youtu.be/aqr4zLZb9sA)

[Universal Constructor](https://youtu.be/MkuEnis1gik)


### Files

To play with this CA in [Golly](https://golly.sourceforge.io/), you'll need two files: the .mc file and the .rule file. You can get these here:

[UC2.mc](https://github.com/andrewbayly/UniversalConstructor/blob/main/UC2.mc)

[N6.rule](https://github.com/andrewbayly/UniversalConstructor/blob/main/N6.rule)













