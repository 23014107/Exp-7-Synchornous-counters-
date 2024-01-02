#  NAME: RAMYA.P
# REFERENCE NO:212223240137

# Exp-6-Synchornous-counters - up counter and down counter 
### AIM: To implement 4 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## UP COUNTER 
The counter is a digital sequential circuit and here it is a 4 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down). 

The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle.
The Counter will be set to Zero when “reset” input is at logic high.
The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down.
The counter will count up when the “up_down” signal is logic high, otherwise count down

Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output.
The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence.
Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1:
Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.

Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.



 
 

Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.

The Q outputs of each flip-flop will serve as the respective binary bits of the final, four-bit count:

 
 

# PROGRAM:
                        module up_counter(clk,q1,q2,q3);
                        input clk;
                        output reg q1,q2,q3;
                        always@(posedge clk)
                        begin
                        q3=(q1&q2)^q3;
                        q2=q1^q2;
                       q1=1^q1;
                       end 
                       endmodule

# RTL :

![293361869-a03a9147-4071-4d8c-b1bb-c94baaacfe25](https://github.com/23014107/Exp-7-Synchornous-counters-/assets/151625620/b9a6db5e-24a6-40eb-8c1a-e2b23f8963fe)

# TRUTH TABLE:
![293361897-0fad4afb-aff2-4a62-8494-e081757ba1ca](https://github.com/23014107/Exp-7-Synchornous-counters-/assets/151625620/86a7909c-9e07-4c70-9b5e-b0d6e021a91f)

# TIMING DIAGRAM FOR UP COUNTER:

![293361908-1fa2cb7e-3c27-4c4e-a7be-71bfbca01bb6](https://github.com/23014107/Exp-7-Synchornous-counters-/assets/151625620/4fa05d89-c38b-4b7d-856e-8a0e7d5d68a1)


## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.
![image](https://user-images.githubusercontent.com/36288975/169644844-1a14e123-7228-4ed8-81a9-eb937dff4ac8.png)




### PROGRAM :
                module COUNTER(clk,q1,q2,q3);
                input clk;
                 output reg q1,q2,q3;
                 always@(posedge clk)
                 begin
                 q3=((~q2)&(~q1))^q3;
                 q2=(~q1)^q2;
                 q1=1^q1;
                 end
                 endmodule

# RTL:

![293361964-aea0bb57-ab87-4549-9720-c26f35609f2d](https://github.com/23014107/Exp-7-Synchornous-counters-/assets/151625620/7fdcf39d-08b3-4055-bbac-77c31e1bda85)


# TRUTH TABLE:

![293361980-e6ff8e0f-9248-4fa0-b05f-cbe39e102dcf](https://github.com/23014107/Exp-7-Synchornous-counters-/assets/151625620/d9741b45-499f-408f-801f-5bc9be02c720)









### TIMING DIGRAMS FOR COUNTER  :



![293361994-169f6ffa-5e86-4212-9451-25c5981e77b0](https://github.com/23014107/Exp-7-Synchornous-counters-/assets/151625620/09ac27fc-cea9-429c-bd24-a89628ea165a)


# RESULT:
Thus synchornous counters up counter and down counter circuit are studied and the truth table for different logic gates are verified.





### RESULTS 
