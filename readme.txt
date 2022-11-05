The files CYSX.lib in this folder should be appended to the CYANA library. This can be done adding the following command to your init.cya file:
append lib CYSX.lib

The following link statement should be included in the .seq file:
link  SG  1 SG 2
Replacing 1 and 2 with the residues relevant for the disulfide bond linkage.
The residue name for CYSS should be changed to CYSX. 


The following can be added to the bottom of your .cya file:

read pdb final.pdb
atoms select "* - &DUMMY"
library rename @CYSX residue=CYS
write pdb peptide.pdb selected all

Replacing "peptide" with the name of the molecule of interest.

The file ssbond.upl is to be modified to contain the residue numbers of the residue that are linked (1 and 2 currently used). The file should then be included as a .upl restraint as usual in cyan.