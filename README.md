# uDR1399-10V-Reference-Standard

Pronounciation: Mew-Dee-Arr-thirteen-ninety-nine
The second revision of the ADR1399 portable bench standard for stable voltage outputs. 

# **Background:**

After the previous version of my ADR1399 standard, the stability left something to be desired. As a result, this version incorporates bootstrapping, an output transistor, and adjustable current limiting. Furthermore, additional ESD protection has been added to the output. The output now incorporates an LT5400 resistor network for gain setting, and as such, is expected to be very stable for the precision gain stage. Two resistors can be used to increase or decrease the gain; although I was not fully after +10.00000V, and wished to have a stable reference first.

Trimming will always be required, as all ADR1399 samples I have recieved in recent times are not close to 7.05V, and usually 6.90V or 6.93V. Care must be taken to use as low temperature coeffecient resistors as possible for trimming, as they introduce extra instabilities to the gain stage.

# **Design:**

