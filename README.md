# mcmd
This is a Monte Carlo / Molecular Dynamics Simulation software.<br />
It works on Linux (tested on Ubuntu) and Mac (tested on OS X El Capitan v10.11.6).<br />

--> MC Currently fully supporting NPT,NVT,NVE,uVT ensembles.  <br />
--> MD supporting NVT.  <br />

PRE-COMPILED EXECUTABLE WORKS WITH THE FOLLOWING COMPILERS:  <br />
&emsp;-> gcc compiler 6.2.0 (circe)  <br />
&emsp;-> gcc compiler 4.9.3 (stampede)  <br />

To download: <br />
`git clone https://github.com/khavernathy/mcmd` <br />

To compile:  (in src dir "src")<br />
`g++ main.cpp -lm -o ../t -I. -std=c++11`  <br />

To run (in base dir "mcmd") <br />
`./t mcmd.inp`<br /><br />  
  
<hr />
  
TODO<br /><br />

-> MC: fix weird NPT bug where ES energy gets really low, quickly
&emsp;-> definitely in the volume-change function..
-> MD: Andersen Thermostat should assign velocity by Boltz-dist., not preset goal value.<br />
&emsp;-> The temp/velocities tend to explode because rando-collisions seem to be forcing molecules to collide.<br />
-> MC: add multi-sorb Qst calculator<br />
-> MC: add LJ Feynmann-Hibbs corrections<br />
-> MC: got polarization working but:<br />
&emsp;-> 4x slower than mpmc. (def. need to make pair lists)<br />
&emsp;-> Aperiodic energy is super low. (high magnitude, negative). Thole field for no PBC may be issue.
-> MC: fix atom-stuck-at-origin issue in uVT<br />
-> MC: make pair lists for MC to run faster AND to do stuff like pressure calculation in MD. <br />
-> MC: fix MC SD's maybe? Seem to be wrong<br />
-> both: NEED TO CHECK IF 4TH POINT OF PLANE MAKES THE SAME PLANE AS PREVIOUS 3 BEFORE MOVING ON<br />
&emsp;-> although I think it's always the case with crystalline systems.<br />
-> MD: Emergent pressure seems large.. (Frenkel method p.84)<br />
-> MD: Use GPU for MD force calculations? (add option)<br />
-> MC: Use GPU for polarization routine (later)<br />
-> MC: Implement Phast2 model?<br />
