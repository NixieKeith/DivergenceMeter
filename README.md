# DivergenceMeter
IN-14 and IN-16 Nixie divergence meter software. 

This is seeded from a clone of the Tom Titor Divergence meter project software version 1.05. http://www.mindspring.com/~tomtitor/#programcode

First repo here is version 2.0 which has added a compiler directive to toggle for an IN-14 nixue or for an IN-16 at compile time. 
Use a #DEFINE IN16 to enable IN-16 logic which just remaps the pins in the software.  Comment-out the N16 define to direct the build to deliver normal IN-14 behavior. A few other tweaks were made. The loop logic was changed for the IN-14 loader routine in an attempt to make the loader a universal function. Timing issues (the cost of usign a table lookup) was too much to make this viable for the IN-16. In other words, using a lookup table AND loop logic in the loader routine costs too many cycles when added on top of the other overhead outside of loader routine. The cost as it stands is stable for the timing, but has little headroom for more workload in the 1 second range (clock lookup time can be exceeded if much more logic is added to the intra-second timings.
