# CPT-singletop

The goal of this program is to estimate the sensibility on detecting CPT-violation at run 2 of LHC.

This is done by running 3 different scripts.

The first scripts "b_mu" :

	- extract the simulated events informations of the root file produced with madgraph through the root Class "Analyzetw" and "root_simu".
	
	- compute the sum of the matrix elements of the vertex of interest in the case of SM and SME with the information extracted from the root file by calling function defined in "matrixSingleTop" and average the value of the ration SME/SM over the number of selected events. The matrix elements should be taking into account the nature of mother and daughter particles. This means it should be able to give right results if the mother particle isn't a top but a charm quark.

	- Integrate the temporal modulation due to the change of referential from SMC to sun-centered on the four components of the averaged ratio SME/SM while assuming the CPT-violation factor "b_mu" = 1.
	
	- Write the resulting 4 functions to root files as TGraph and plot f(t) over 24h.
	
The second scripts "sensibility" :

	- Create the histograms needed to compute the X^2 for the "b_mu" factor by using the results of (CMS PAS TOP-17-023) scaled to the luminosity of interest from 36 fb^-1 to 150 fb^-1.
	
	- Plot the histogram with the sources of backgrounds considered and plot the estimated temporal modulation for the signal.
	
The third scripts "Xcarre" :

	- Takes the histograms produced by sensibility as inputs and compute the X^2 function that can be found slide 12 of the Slideapp.pdf and fits a pol2 function on the points.
	
	- Plot the X^2 function.

How to use the program :

The program is divided in 3 part :

1 - Open the b_mu.cpp script:
	-Change the name of the root files at line 52, 54 for the study of t-channel and line 148, 150 for the tw-channel to match those of your files.
	-Change the value of the energy to match your simulation in the strin nameFile line 249.
	
2 - Open the sensibility.cpp script:
	-Change the name of the file line 17 to match the energy of your simulation.

3 - Compile the program with the : "make" command in "SingleTopPheno-master" directory.

4 - Put your MadGraph root files in the "data" directory.

5 - Run 2 times "./bin/b_mu" from "SingleTopPheno-master" directory and enter "t" for the first run and then "tbar" for the second run.

6 - Run "./bin/sensibility". Make sure you ran both particle and antiparticle parts of the channel you are studying through "b_mu". And delete the modulation files between two runs of the same choices in "b_mu".

7 - Run "./bin/Xcarre"
