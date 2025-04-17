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

2. Nativigate to the folder that you have downloaded the scripts and data into (e.g., /Users/yourname/Documents/workshop/):
   ```bash
   cd /Users/yourname/Documents/workshop/
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

First, install WSL (Windows Subsystem for Linux)

1. Open PowerShell as Administrator (Type it in your 
   Run the following command:
   ```bash
    wsl --install
   ```

This will:

  Install WSL2<br>
  Install Ubuntu (default)<br>
  Set up necessary components

When prompted, restart your computer

2. Set up Ubuntu in WSL

After reboot, Ubuntu will open automatically. Wait for installation to complete then choose a username and password when prompted. This opens a Linux terminal (Ubuntu shell).

3. Install Miniconda inside WSL (Ubuntu)

In the Ubuntu terminal, run the following:
```bash
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O miniconda.sh
bash miniconda.sh
```

Accept the license agreement and confirm the default install location (e.g., /home/yourname/miniconda3)/

When installation finishes, close and reopen the terminal or run:
```bash
source ~/.bashrc
```

Check that Conda is available:
```bash
conda --version
```

4. Move Setup Scripts Into WSL. Place the files (Install_programs.sh, workshop_env.yml, install_r_github.R) in a folder on Windows (e.g., C:Users\yourname\Documents\workshop).

In the Ubuntu terminal, navigate to that folder:
```bash
cd /mnt/c/Users/yourname/Documents/workshop/
```

6. Run the following command:

```bash
bash Install_programs.sh
```

After around 5-10 minutes, you should now have a conda environment called 'bioinfo-workshop' and you can run all the analysis from here.

To enter this conda environment, open your terminal, navigate to the folder with the data and scripts, and enter the following command:
  ```bash
  conda activate bioinfo-workshop
  ```





<br>

## Please attempt to download all data and software prior to the course start. If you have any issues, please get in [contact](mailto:b.sobkowiak.12@ucl.ac.uk).

Click [here](README.md) to return to the course homepage.
