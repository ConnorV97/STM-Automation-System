# STM-Automation-System
Scanning Tunneling Miscoscope (STM) Automation System for automating scanning, bias spectroscopy, temperature and magnetic field ramping to characterize the local denisty of states (LDOS) of supercondcuting materials. 
This Automaton System was designed to for a Nanonis controlled Unisoko 1300 STM. The Nanonis controller utilizes a LabVIEW interface developed by National Instruments.
Therefore, the automatino system was developed utilizing LabVIEW. To implement the key automation workflow the Queued Message Handler Architecutre was utilized. 
Specifically, the Producer-Consumer framework. This framework allows complete control over the sequence of the experiment and allows for multiple instruments to be implemented.
For example, for this system we utilized the Unisoku STM, the Lakeshore Model 50 Temperature contoller and the Cryogenic Magnet Power Supply. 

The idea behind this system is to automate the scanning and bias spectrocsopy of the STM. While also being able to update the scan frame center and bias position following a temperature or magnetic field change.
This system takes advantage of the instrument drivers created by Nanonis, Lakeshore and Cryogenic. Thus allowing for robust instrument control and the ability to create custom experiments.
The experiment in which this system was designed for was to analyze how the superconducting gap of conventional superconductors change as a function of magnetic field and temperature. 
This system is coupled with Python to perform image analysis through flattening and denosing the images then, determining the drift between two iamges utilizing the Fourier Phase Correlation. 
