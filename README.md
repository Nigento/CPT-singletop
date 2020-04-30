# CPT-singletop

How to use the program :

To 
The program is divided in 3 part :

 1 - The b_mu.cpp script:
	Open the b_mu.cpp script:
		-Change the name of the root files at line 52, 54 for the study of t-channel and line 148, 150 for the tw-channel to match those of your files.
		-Change the value of the energy to match your simulation in the strin nameFile line 249.
	
	Open the sensibility.cpp script:
		-Change the name of the file line 17 to match the energy of your simulation.

 2 - Compile the program with the : "make" command in "SingleTopPheno-master" directory.

 3 - Put your MadGraph root files in the "data" directory.

 4 - Run 2 times "./bin/b_mu" from "SingleTopPheno-master" directory and enter "t" for the first run and then "tbar" for the second run.

 5 - Run "./bin/sensibility"

 6 - Run "./bin/Xcarre"
