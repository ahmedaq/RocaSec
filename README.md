# RocaSec

&nbsp;
## Table of Contents
*  [Overview](#overview)
*  [Details](#details)
*  [Requirements](#requirements)
*  [Installation](#installation)
*  [Usage](#usage)
*  [Acknowledgement](#acknowledgement)
*  [Troubleshooting](#troubleshooting)
*  [Citation](#citation)

&nbsp;
## Overview
RocaSec is a standalone cross-platform package which features an easy-to-use GUI. The package only requires the multiple sequence alignment data of a protein for inferring the underlying co-evolutionary sectors. In addition, when information on the protein biochemical domains is provided, RocaSec returns the corresponding statistical association between inferred sectors and biochemical domains.

![alt text][RocaSecGUI]

[RocaSecGUI]: https://github.com/ahmedaq/RocaSec/blob/master/fig_ns34a_v2.png "RocaSec GUI"

&nbsp;
## Details
#### Title of paper
RocaSec: A standalone GUI-based package for robust co-evolutionary analysis of proteins
#### Authors
Ahmed A. Quadeer, David Moarles-Jimenez, and Matthew R. McKay

&nbsp;
## Requirements
A PC with either macOS, Microsoft Windows, or Linux.

&nbsp;
## Installation

1.  Download the appropriate installer for your operating system from
https://github.com/ahmedaq/RocaSec. The installer file is named as “RocaSec_x”, where x is the name of the operating system.

2.  Install it by following the guidelines in the setup window. This will also install MATLAB runtime libraries required to run the app (if not already installed). This procedure may take 10–15 minutes depending on the internet connection.

    [Important note]: Ignore any instruction that appears in the setup window after the installation is finished.

3.	Run the installed app by double clicking “RocaSec” located in the default location: 

    a.	/Applications/RocaSec/application/ in macOS, 

    b.	C:\Program Files\RocaSec\application\ in Microsoft Windows, or

    c.	/usr/RocaSec/application in Linux. 

    This will open the GUI of the RocaSec software.

    [Important note]: For Linux users, in case the app does not open by the method mentioned above, open the Terminal and go to the directory where the application is installed and type the following command: 
      ```
      ./run_RocaSec.sh /"path"/MATLAB_Runtime/v96/
      ```
      where “path” is the directory in which MATLAB Runtime has been installed. For example, if MATLAB Runtime libraries are installed in the directory /home/UserName/Documents/MATLAB_Runtime/ (where “UserName” is the name of user’s home directory), the code to run the software will be:
      ```
      ./run_RocaSec.sh /home/UserName/Documents/MATLAB_Runtime/v96/
      ```

&nbsp;
## Usage

1.	To infer sectors of co-evolving sites using RocaSec, you need to simply provide the following data and click “Run RoCA” button in the GUI:
      * Aligned sequence data in the FASTA format [mandatory].
      
        If sequence data is not aligned, the user can use one of the following free alignment programs: (i) Multiple Alignment using Fast Fourier Transform (MAFFT; https://mafft.cbrc.jp/alignment/server/) or (ii) MUltiple Sequence Comparison by Log- Expectation (MUSCLE; https://www.ebi.ac.uk/Tools/msa/muscle/).
        
        Format specifics: Header information (in any format) starting with “>”, following immediately with the sequence in the next line. File extension should be either “.fasta”, “.fa”, “.faa”, “.fas”, or “.txt”.

      * A list of protein biochemical domains in xls or xlsx format [optional]. 
        
        If provided, the software computes and displays the association of inferred sectors with the specified biochemical domains. The numbering of the residues in each biochemical domain should match the numbering used in the MSA.
        
        The “xls” or “xlsx” file should be formatted as follows: each column should represent a specified biochemical domain and should include (1) the name of the biochemical domain in the first row (as a text field), and (2) the sites involved in the biochemical domain, given as numerical values in the subsequent rows. Also, see the example files provided in the Data_RoCA folder in this repository. 

        
      * Maximum number of PCs to use in the inference procedure [default = 6]. 
      
        Once the processing is finished, the user can tune the interactive slider to visualize in real-time the sectors inferred when different number of PCs are provided to the RoCA method. Note that all the outputs (all the inferred sectors and associations) change when the number of PCs is modified.
        
      * 3D protein structure PDB ID (4 digits ID; e.g., 4u5w) [optional]. 
        
        If a valid PDB ID in the “input information” panel is provided (validity of the PDB ID is checked automatically by querying the protein data bank,  https://www.rcsb.org, and reported in the processing information panel), a script in “.pml” format is generated in the output directory which the user can directly run in PyMol—a widely-used software for molecular visualization. The steps involved in mapping the alignment indices to the protein sequence present in the PDB file is as follows:

        First, the sequence (as well as residue numbering) for which the structure is present in the PDB file is extracted, it is then aligned with the consensus sequence of the MSA to generate a mapping from MSA positions to the residue numbering in PDB file (a warning is displayed in the processing information panel if the alignment score—computed using the standard BLOSUM50 scoring matrix—is less than zero), and then this mapping on the inferred sectors is used to generate the PyMol scripts. The alignment of the consensus sequence of the MSA with the sequence in the PDB file as well as the resulting mapping of MSA positions are provided as additional output files when the user provides the PDB ID input. 
        
        To inform the user about this generated .pml script, a new window is opened in the GUI with: 1) a link to the PyMol webpage for downloading the PyMol software (available at https://pymol.org/), and 2) brief detail on the simple procedure to run the PyMol script.

2.	For testing purposes, you can use the data provided in the Data_RoCA folder in this repository. 

3.	RocaSec software saves the following output files:
      * Sample PCs used in the inference procedure (xyz_SamplePCs.format, where “xyz” is the name of the fasta file provided as an input and “format” is either csv or xls depending on the option selected in the GUI.)
      * Eigenvalues of the sample correlation matrix (xyz_Eigenvalues.format)
      * RoCA estimated PCs (xyz_RocaPCs.format)
      * RoCA sectors (xyz_RoCASecs.format), with each row representing a sector.
      * Vector graphics (eps format) of all results are also saved in the same directory for generating publication-quality figures.
      * In case the user provides a PDB ID of the protein structure:
      
        -- Alignment of the sequence for which structure is present in the PDB file and the consensus sequence of the MSA (xyz_alignment_pdbseq_Cseq.txt).
        
        -- Index mapping of the MSA to the indexing used in the sequence for which structure is present in the PDB file (xyz_mapping_msa_pdb.format).
        
        -- Pymol compatible “.pml” file (pymol_xyz_secs_numPCs#.pml, where # is the number of PCs used to infer sectors). Note: The user has to install Pymol separately. The structure can be visualized by opening PyMol, clicking File -> Run Script, and selecting the generated .pml file. 
      
    Note that the above-mentioned output files are saved by default in a new subdirectory named “xyz” within the directory in which the input fasta file is located.

&nbsp;
## Acknowledgement

We would like to thank Neelkanth Kundu, Laureano Moreno Pozas, Muhammad Saqib Sohail, Syed Muhammad Umer Abdullah, Syed Faraz Ahmed, and Syed Awais Wahab Shah for providing useful comments/feedback and assisting in testing of RocaSec. 

&nbsp;
## Troubleshooting
For any questions or comments, please email at ahmedaq@gmail.com. 

&nbsp;
## Citation
#### Plain text
Ahmed A Quadeer, David Morales-Jimenez, Matthew R McKay, RocaSec: A standalone GUI-based package for robust co-evolutionary analysis of proteins, <i>Bioinformatics<\i>, btz890, https://doi.org/10.1093/bioinformatics/btz890
#### BibTeX
@article{Quadeer2019,
author = {Quadeer, Ahmed A. and Morales-Jimenez, David and McKay, Matthew R.},
doi = { },
journal = {Bioinformatics},
month = {nov},
number = { },
pages = { },
title = {{RocaSec: A standalone GUI-based package for robust co-evolutionary analysis of proteins}},
url = { },
volume = { },
year = {2019}
}
