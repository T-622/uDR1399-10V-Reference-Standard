# uDR1399-10V-Reference-Standard

Pronounciation: Mew-Dee-Arr-thirteen-ninety-nine. \nThe second revision of the ADR1399 portable bench standard for stable voltage outputs. 

# **Background:**

After the previous version of my ADR1399 standard, the stability left something to be desired. As a result, this version incorporates bootstrapping, an output transistor, and adjustable current limiting. Furthermore, additional ESD protection has been added to the output. The output now incorporates an LT5400 resistor network for gain setting, and as such, is expected to be very stable for the precision gain stage. Two resistors can be used to increase or decrease the gain; although I was not fully after +10.00000V, and wished to have a stable reference first.

Trimming will always be required, as all ADR1399 samples I have recieved in recent times are not close to 7.05V, and usually 6.90V or 6.93V. Care must be taken to use as low temperature coeffecient resistors as possible for trimming, as they introduce extra instabilities to the gain stage.

# **Design:**

## **Power Supply:**
Much has stayed from the previous design's power supply (See: [uDR1399 Rev01](https://github.com/T-622/ADR1399-10V-Bench-Standard/tree/main)). The LT3045 is a very good regulator when used properly. One issue I encountered often with the design is that hotplugging power supplies at ~18V with the L, C, and R of the power cables can cause transients large enough to exceed the absolute +22V maximum for the LT3045's inputs. This issue can be resolved through a soft-start circuit using an RC circuit to charge the gate of a p-channel FET, or an appropriate TVS diode. I have not placed these in the design, as my power supply ramps without ringing, and 2x 9V batteries seem to work reasonably well. 

The board's manual power mux is located in the top left corner, and can select from an external 15V regulated supply, or an unregulated 16-20V input fed to the LDO.
