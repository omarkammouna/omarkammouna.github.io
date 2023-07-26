---
title : Setting up the Preconfigured BAYCII Labs WSL 
by : Wassim Derbel
---
# Tutorial: Setting up the Preconfigured BAYCII Labs WSL Environment

In this tutorial, we'll guide you through the process of setting up the preconfigured BAYCII Labs Windows Subsystem for Linux (WSL) environment. This environment comes with Python, Docker, and other tools preinstalled, making it a great starting point for your development needs. Let's get started!
## Step 1: Install WSL on WINDOWS
1. Enable WSL2**
   - Open PowerShell as an administrator.
   - Run the command: `wsl --install`.
   - Wait for the installation to complete.
## Step 2: Download the WSL Packed File


1. Visit the following link to download the preconfigured WSL packed file**:
   [Download BAYCII Labs WSL](https://drive.google.com/file/d/1iI9GLPQ4HLxKirTIefu5lfEq9MELm6Sm/view?fbclid=IwAR32xSzgcx7u6N4AgxiV9csx4g3EavY-FQ5e4WbKGv1GOYYpIkPphteU8w8)

2. Save the downloaded file to a location on your computer**.

## Step 3: Open Git Bash or Equivalent

1. Open Git Bash or any other terminal emulator of your choice on your Windows machine**.

## Step 4: Remove Existing WSL Distributions

1. Run the command below to list all registered WSL distributions on your machine**:


```
wsl --list
```

2. Identify the names of the existing WSL distributions that you want to remove. 


3. To remove a specific distribution, use the following command (replace `<distributionName>` with the name of the distribution you want to remove)**:


```
wsl --unregister <distributionName>
```

> Note : Repeat this command for each distribution you want to remove.

## Step 5: Import a Custom WSL Environment (Optional)

1. If you don't have the BAYCII Labs WSL packed file, you can create your custom WSL environment. Follow the WSL distribution installation instructions for the Linux distribution of your choice. 

## Step 6: Access Your Custom WSL Environment

1. Once you have your desired WSL distribution installed or imported, you can run the following command to enter the WSL environment**:

```
wsl 
```

2. You are now inside your WSL environment, where you can install Python, Docker, and other tools based on your preferences. 

## Step 7: Using Sudo Password

1. If you need administrative privileges (e.g., for system-level changes), you will be prompted to enter a password. The sudo password for this preconfigured environment is xftekko. 

**Congratulations!** You have successfully set up your custom WSL environment on your Windows machine. Enjoy developing
