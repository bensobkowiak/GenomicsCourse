# Genomic Analysis and Phylodynamics Workshop

## Pre-course Instructions

Please following these instructions to download all programs and data for the course. You will require ~ 1GB of space to install all programs and data.

### Data and Scripts

Please download all data and scripts required for this course by clicking the following link (Note, the file size is ~ MB) and saving all the data and scripts contained in a folder on your computer.

[Download Data and Scripts](https://drive.google.com/drive/folders/1w3WG0jCj9BfB6aMB2Kq7vC2Yfx1ck6NB?usp=share_link)
<br>

### Programs and software

#### Mac and Linux users

The easiest method for downloading all the software required for the workshop is to first download miniconda. 

Mac users, please following these instructions:

1. Open the Terminal.

2. Enter the following code: 

  ```bash
  # Download and install Miniconda
  wget https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.sh -O ~/miniconda.sh
  bash ~/miniconda.sh -b -p $HOME/miniconda

  # Follow prompts, then restart terminal
  ```

Linux users, please follow these instructions:

1. Open the Terminal.

2. Enter the following code: 

  ```bash
  # Download and install Miniconda
  wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda.sh
  bash ~/miniconda.sh -b -p $HOME/miniconda

  # Follow prompts, then restart terminal
  ```

Following the link to download the scripts above, you should have downloaded three scripts - Install_programs.sh, workshop_env.yml, and install_r_github.R. These are the three scripts required to download all the programs required for the workshop.

1. Open your terminal again.

2. Nativigate to the folder with the scripts in (change the /path/to/folder/ to the folder you have these stored in):
   ```bash
   cd /path/to/folder/
   ```
3. Run the following command:
   ```bash
   ./Install_programs.sh
   ```

After around 5-10 minutes, you should now have a conda environment called 'bioinfo-workshop' and you can run all the analysis from here.

To enter this conda environment, open your terminal, navigate to the folder with the data and scripts, and enter the following command:
  ```bash
  conda activate bioinfo-workshop
  ```

#### Windows users

For windows users, it is a little more complicated to install miniconda. 

1. Install WSL (Windows Subsystem for Linux)

Open PowerShell as Administrator
  Run the following command:
  wsl --install

This will:
  Install WSL2
  Install Ubuntu (default)
  Set up necessary components

When prompted, restart your computer
2. Set up Ubuntu in WSL

After reboot, Ubuntu will open automatically
Wait for installation to complete
Choose a username and password when prompted
This opens a Linux terminal (Ubuntu shell)
3. Install Miniconda inside WSL (Ubuntu)

In the Ubuntu terminal, run the following:
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O miniconda.sh
bash miniconda.sh
Accept the license agreement
Confirm the default install location (e.g., /home/yourname/miniconda3)
When installation finishes, close and reopen the terminal or run:
source ~/.bashrc
Check that Conda is available:
conda --version
4. Move Setup Scripts Into WSL

Place your files (setup_conda_workshop.sh, workshop_env.yml, install_r_github.R) in a folder on Windows (e.g., C:\Users\YourName\Documents\bioinfo_setup)
In the Ubuntu terminal, navigate to that folder:
cd /mnt/c/Users/YourName/Documents/bioinfo_setup
5. Run the Workshop Setup Script

From within that directory, run:
bash setup_conda_workshop.sh
This will:
Create the Conda environment
Install required packages
Run the R setup script
6. Activate the Environment (if needed)

If you want to manually activate the environment later:
conda activate bioinfo-workshop





<br>

## Please attempt to download all data and software prior to the course start. If you have any issues, please get in [contact](mailto:b.sobkowiak.12@ucl.ac.uk).

Click [here](README.md) to return to the course homepage.
