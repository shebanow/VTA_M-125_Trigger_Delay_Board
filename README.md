# VTA_M-125_Trigger_Delay_Board

The VTA M-125 amp is a great, 125w tube-based audio amplifier (monoblock). Available in kit form or preassembled from 
http://www.tubes4hifi.com/bob.htm#M125. 

One thing lacking in the amp is a 12v audio trigger capability. So, I modified the amp design to include a trigger board that can also function as a power delay for the plate power (main power in the amp). This is similar to the "Time Delay Relay" board sold on Tubes4HiFi.com except it also adds 12v trigger capability.

Available in this reposistory are:
* Gerber files for a PCB 
* PDFs for the schematic and chassis layout
* Autodesk Eagle project files
* Complete BOM (bill of materials) (I used Digikey to purchase parts)
* Instructions (below) on how to install it.

# Installation instructions

To install this board, follow these directions:
1. Order PCBs using the Gerber files included in this repository. This design uses 2-layer PCBs and includes a part layout silkscreen.
2. Order parts using the BOM from your favorite parts distributor. 
3. Machine the chassis using the PDF drawing included in this repository. 
4. Once you have both PCBs and parts, assemble the trigger/delay board. I used small solder lugs to attach wires to my board, but in theory, you could dispense with that and solder wires directly to the through holes (though w/ 14 gauge wires, could be a trick).
5. Install the 3.5mm trigger connector in the chassis between the RCA input jack and the speaker lugs.
6. Install the trigger/delay board in the chassis using small M3 screws and standoffs. Attach the boards using M3 washers and lock nuts
    * For the standoffs, I used https://www.digikey.com/product-detail/en/raf-electronic-hardware/M2141-3005-SS/1772-2025-ND/7681436
    * For the M3 screws, you could use https://www.digikey.com/product-detail/en/w-rth-elektronik/97790403211/732-13707-ND/10056390 (nylon) or in my case, https://www.amazon.com/gp/product/B00F31QQYU/ref=ppx_yo_dt_b_asin_title_o07_s00?ie=UTF8&psc=1 (black).
7. Prior to starting the WIRING instructions on page 5 of the assembly instructions, perform these steps:
    * Twist a pair of 24" long red and black, 14-gauge stranded hookup wires. On one end of the pair, leave roughly 3" untwisted, and on the other end, 4" untwisted. Strip the 3" end of each wire 1/2". Strip the red wire of the 4" end 1/2" as well, but only strip the black end 3/8". 
    * Cut a 8" long red, 14-gauge stranded hookup wire. Strip 1/2" on one end and 3/8" on the other. 
    * Separate the wires in the 4" end of the first twisted pair. Twist the 8" wire with the red wire of the first twisted pair, end-to-end. At the junction of the red and black wires of the longer twisted pair, now twist the remainder of the 8" red wire with the black wire of the longer twisted pair. At the completion of this step, the red and black wires should line up.
    * Starting with the 3" end, attach the twisted pair assembly along the inside chassis from the fuse folder (black wire end), behind the power transformer, along the left edge (see machining diagram for definition of "left"), to the left of the tube sockets, then along the front to the power switch. You can use wire ties to hold the cable to the chassis if necessary.
    * Solder the black wire on the 3" end to the outer lug of the fuse holder. Solder the red wire of the same end to the "left upper" lug of the IEC power connector. Use a small 3" (or so) 14 gauge wire to connect the other upper lug of the IEC connector to the outside lug of the fuse holder. Follow the instructions in the manual for connecting the chassis lug (ground) of the IEC connector.
    * On the 4" end of the twisted pair assembly, solder one red wire to the lower lug of the power switch and one red wire to the other lug; the order doesn't matter. Solder the black wire to the "AC_COMM" lug of the trigger/delay board. Solder the other end of the 8" wire to the "AC_LINE" lug of the trigger/delay board.
8. Connect the trigger.
    * Twist a set of three 14" 22-gauge hookup wires. Preferrably, green, black, and red, but if only one color is available, be sure to mark the wires on each end so you know which wire is which. Strip one end to 3/8" and the other to 1/2". 
    * Extend the twisted set between the trigger/delay board "TRIG_xxx" pins and the 3.5mm trigger jack, running the cable along the back-inside of the chassis past the fuse holder and IEC power conector, then up along side the right side of the power transformer and on to the trigger board. 
    * Starting with 
9. At this point, the trigger/delay board is testable. 
    * Plug in an **UNCONNECTED** 12v trigger cable into the trigger jack on the rear panel. Plug in the power cable to the chassis, being **VERY CAREFUL** about high voltage now in the chassis. With the power switch on, you should see the LED light on the trigger/delay board light up red. You should also be able to measure roughly 12v DC between the "TRIG_RING" and "TRIG_GND lugs on the trigger/delay board. If the light does not light up, check the fuse, then check the board for shorts, then each part of proper insertion - standard board debugging. 
    * Unplug the trigger cable from the trigger jack. You should see the LED light blue, then after a delay, light to green. Adjust the potentiometer on the trigger delay board to get the desired turn on-delay (time in blue state). The delay should be adjustable from short (~1 sec) to long (~27 sec). You can test this by turning the amp on and off with the main power switch. During the delay period, the LED will light blue. If a solid state rectifier is used, a 17 sec delay is recommended. If a tube rectifier is use, a short delay (1 sec) is ok, but you cna set this as desired. As designed, it is not possible to have no delay. 
    * If all is well, unplug power.
10. Instead of hooking up the red power transformer wires as stated in step 2 of the WIRING instructions on page 5, do the following:
    * Twist the pair of RED leads from the power transformer together and extend to the "TRANS_RED1" and "TRANS_RED2" lugs of the trigger/delay board. Shorten as needed, stripping 3/8" from each end. Solder to the "TRANS_RED1" and "TRANS_RED2" lugs (doesn't matter which wire goes to which). 
    * Twist a pair of RED, 22 gauge hookup wires, length as needed, to connect the "V5_PIN4" and "V5_PIN6" lugs on the trigger/delay board to the #4 and #6 lugs of the V5 tube. Strip one end of the pair to 3/8" and the other to 1/2". Solder the 3/8" end to the "V5_PIN4" and "V5_PIN6" lugs on the trigger/delay board and the other 1/2" end to the 4 and #6 lugs of the V5 tube. Wire order does not matter.
