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

&nbsp;
## Overview
RocaSec is a standalone cross-platform package which features an easy-to-use GUI. The package only requires the multiple sequence alignment data of a protein for inferring the underlying co-evolutionary sectors. In addition, when information on the protein biochemical domains is provided, RocaSec returns the corresponding statistical association between inferred sectors and biochemical domains.

![alt text][RocaSecGUI]

[RocaSecGUI]: https://github.com/ahmedaq/RocaSec/blob/master/RocaSec2.png "RocaSec GUI"

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
<details>
  <summary>
    <b> macOS </b>
  </summary>  
&nbsp;

RocaSec can be installed using one of the following methods on macOS:

#### Method 1: Downloading MATLAB Runtime separately and running directly the RoCA app without any installation

1. Download and install the Macintosh version of the MATLAB Runtime for R2017b from the following link on the MathWorks website http://ssd.mathworks.com/supportfiles/downloads/R2017b/deployment_files/R2017b/installers/maci64/MCR_R2017b_maci64_installer.dmg. This will install MATLAB Runtime at /Applications/MATLAB/MATLAB_Runtime. Note that the RoCA application will not work with any older or newer version of the MATLAB Runtime.

2. Download this "RocaSec" repository. A folder named "RocaSec-master" will be made on your computer.

3. To run the app, open terminal, go to the newly created folder /RocaSec-master/macos/ directory and type the following command:
    ```
    ./run_RocaSec.sh /Applications/MATLAB/MATLAB_Runtime/v93/
    ```
This will open the GUI of the RocaSec software.


#### Method 2: Using the MATLAB Runtime installer

1.	Download the installer "RocaSec_mcr" from http://bit.ly/RocaSec_v1_macOS (size: ~1 GB) and install the application by following the guidelines in the setup window as follows:
      * Make sure to install RocaSec in any folder other than the “Applications” folder (e.g., you can create a new folder on your Desktop or in Documents folder). In this tutorial, we assume that you made a folder “RoCA_dir” in your “Documents folder”.
      * Do not change the default installation folder ("Applications") of MATLAB runtime libraries. 
      * This will install RoCA_gui as well as MATLAB runtime libraries (required to run the app). This procedure may take 2 – 3 minutes on a standard computer.

2.	To run the app, open terminal, go to the newly created folder /Documents/RoCA_dir/applications/ directory and type the following command:
    ```
    ./run_RocaSec.sh /Applications/MATLAB/MATLAB_Runtime/v93/
    ```
This will open the GUI of the RocaSec software.
</details>

<details>
  <summary>
    <b> Windows </b>
  </summary>  
&nbsp;

RocaSec application can be installed using one of the following methods on Microsoft Windows OS:

#### Method 1: Downloading MATLAB Runtime separately and running directly the RoCA app without any installation

1.	Download and install the Windows version of the MATLAB Runtime for R2018a from the following link on the MathWorks website http://ssd.mathworks.com/supportfiles/downloads/R2018a/deployment_files/R2018a/installers/win64/MCR_R2018a_win64_installer.exe. This will install MATLAB Runtime in the Program Files directory. Note that the RoCA application will not work with any older or newer version of the MATLAB Runtime.

2. Download this "RocaSec" repository. A folder named "RocaSec-master" will be made on your computer.

3. Go to \RocaSec-master\windows\ directory and run the RoCA app by double clicking “RocaSec.exe” in this folder. This will open the GUI of the RoCA software. 
    
    Note that antivirus programs, if installed, may block running the software. If this problem arises (noticed for example in the case of Avast and F-secure antivirus), add the program in trusted applications and then run it.

#### Method 2: Using the MATLAB Runtime installer

1.	Download the installer "RocaSec_mcr" from http://bit.ly/RocaSec_v1_win (size: ~1 GB) and install the application by following the guidelines in the setup window as follows:
      * Make sure to install RocaSec in any folder other than the “Program Files” folder (e.g., you can create a new folder on your Desktop or in Documents folder). In this tutorial, we assume that you made a folder “RoCA_dir” in your “Documents folder”.
      * Do not change the default installation folder (“Program Files”) of MATLAB runtime libraries. 
      * This will install RocaSec as well as MATLAB runtime libraries (required to run the app). This procedure may take 2 – 3 minutes on a standard computer.

2.	Run the installed app by double clicking “RocaSec.exe” located in your newly created folder (e.g.,\Documents\RoCA_dir\application\). This will open the GUI of the RocaSec software. 
    
    Note that antivirus programs, if installed, may block running the software. If this problem arises (noticed for example in the case of Avast and F-secure antivirus), add the program in trusted applications and then run it.

</details>

<details>
  <summary>
    <b> Linux </b>
  </summary>  
&nbsp;

RocaSec application can be installed using one of the following methods on Linux OS (tests have been done on CentOS Linux 7, Ubuntu 16.04 LTS and 18.04 LTS):

#### Method 1: Downloading MATLAB Runtime separately and running directly the RoCA app without any installation

1.	Download the Linux version of the MATLAB Runtime for R2018a from the following link on the MathWorks website: http://ssd.mathworks.com/supportfiles/downloads/R2018a/deployment_files/R2018a/installers/glnxa64/MCR_R2018a_glnxa64_installer.zip. 

      Unzip the downloaded zip file in a folder (e.g., MCR_downloaded). Open terminal, go to the directory of the downloaded zip file and type the following commands (admin password on user's computer required): 
      ```
      sudo chmod +x install
      ./install
      ```
      This will open the MATLAB Runtime setup window. Follow the guidelines in the setup window and install MATLAB Runtime in the directory /Documents/MATLAB_Runtime. Note that the RoCA application will not work with any older or newer version of the MATLAB Runtime.

2. Download this "RocaSec" repository. A folder named "RocaSec-master" will be made on your computer.
3. Open terminal and go to /RocaSec-master/Linux/ directory and type the following command (admin password on user's computer required): 
      ```
      sudo ./run_RocaSec.sh /home/UserName/Documents/MATLAB_Runtime/v94/
      ```
      where “UserName” is the name of the directory in which the Documents folder is located. This will open the GUI of the RocaSec software.

#### Method 2: Using the MATLAB Runtime installer

1.	Install the RocaSec application as follows:
      * Download the installer "RocaSec_mcr.install" from http://bit.ly/RocaSec_v1_linux (size: ~1 GB) to a directory on your computer. Here onwards, we assume that you download it in the "Documents" folder.
      * Open terminal and go to the "Documents" folder and type the following command (admin password on user's computer required): 
      ```
      sudo chmod +x RocaSec_mcr.install
      ```
      * Go to the "Documents" folder, double click on the installer file “RocaSec_mcr.install”, and follow the guidelines in the setup window.
      * Please make sure to install RocaSec in any folder other than the system folders (e.g., you can create a new folder on your Desktop or in Documents folder). In this tutorial, we assume that you made a folder “RoCA_dir” in your “Documents folder”.
      * Install MATLAB Runtime in the directory /Documents/MATLAB_Runtime/.
      * This will install RocaSec as well as MATLAB runtime libraries (required to run the app). This procedure may take 2 – 3 minutes on a standard computer.

2.	To run the application, open terminal and go to the directory /Documents/RoCA_dir/application/ and type the following command (admin password on user's computer required): 
      ```
      sudo ./run_RocaSec.sh /home/UserName/Documents/MATLAB_Runtime/v94/
      ```
      where “UserName” is the name of the directory in which the Documents folder is located. This will open the GUI of the RocaSec software.
</details>


&nbsp;
## Usage

1.	To infer sectors of co-evolving sites using RocaSec, you need to simply provide the following data and click “Run RoCA” button in the GUI:
      * Aligned sequence data in the FASTA format [mandatory].
      
        If sequence data is not aligned, the user can use one of the following free alignment programs: (i) Multiple Alignment using Fast Fourier Transform (MAFFT; https://mafft.cbrc.jp/alignment/server/) or (ii) MUltiple Sequence Comparison by Log- Expectation (MUSCLE; https://www.ebi.ac.uk/Tools/msa/muscle/).

      * A list of protein biochemical domains in xls or xlsx format [optional]. 
        
        If provided, the software computes and displays the association of inferred sectors with the specified biochemical domains. The xls or xlsx file should be formatted as follows: each column should represent a specified biochemical domain and should include (i) the name of the biochemical domain in the first row (as a text field), and (ii) he sites involved in the biochemical domain, given as numerical values in the subsequent rows. See the example files provided in the Data_RoCA folder in this repository.
        
      * Maximum number of PCs to use in the inference procedure [default = 6]. 
      
        Once the processing is finished, the user can see sectors inferred from different number of PCs using the interactive slider.
        
      * 3D protein structure PDB ID (4 digits ID; e.g., 4u5w) [optional]. 
        
        If provided, a Pymol compatible “.pml” file is generated at the output, which can be used to visualize the biochemical domains (if provided) and the inferred sectors (for different number of PCs input) on the 3D protein structure. Note that the user has to install Pymol (available at https://pymol.org/) separately.


2.	For testing purposes, you can use the data provided in the Data_RoCA folder in this repository. 

3.	RocaSec software saves the following output files:
      * Sample PCs used in the inference procedure (xyz_SamplePCs.format, where “xyz” is the name of the fasta file provided as an input and “format” is either csv or xls depending on the option selected in the GUI.)
      * Eigenvalues of the sample correlation matrix (xyz_Eigenvalues.format)
      * RoCA estimated PCs (xyz_RocaPCs.format)
      * RoCA sectors (xyz_RoCASecs.format)
      * Pymol compatible “.pml” file (pymol_xyz_secs_numPCs#.pml, where # is the number of PCs used to infer sectors). Note: The user has to install Pymol separately. The structure can be visualized by opening PyMol, clicking File -> Run Script, and selecting the generated .pml file. 
      * Vector graphics (eps format) of all results are also saved in the same directory for generating publication-quality figures.

    Note that the above-mentioned output files are saved by default in a new subdirectory named “xyz” within the directory in which the input fasta file is located.

&nbsp;
## Acknowledgement

We would like to thank Neelkanth Kundu, Laureano Moreno Pozas, Muhammad Saqib Sohail, Syed Muhammad Umer Abdullah, Syed Faraz Ahmed, and Syed Awais Wahab Shah for providing useful comments/feedback and assisting in testing of RocaSec. 

&nbsp;
## Troubleshooting
For any questions or comments, please email at ahmedaq@gmail.com. 
