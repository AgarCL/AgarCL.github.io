---
layout: "contents"
title: Installation Instructions
---

# Installation Instructions

The recommended way to use AgarCL is within a Docker container running a Linux OS. This ensures there are no conflicts with other installed packages or platforms. This installation script will allow you to interact with AgarCL in a headless mode.

## Setting up the container
Follow these steps to set up the container:

1. **Download the Dockerfile**
   - Download the [Dockerfile.txt](https://github.com/AgarCL/AgarCL/blob/main/Dockerfile.txt).

2. **Navigate to the Directory Containing the Dockerfile**
   - Open your terminal and navigate to the folder where the `Dockerfile.txt` is located:
     ```bash
     cd /path/to/Dockerfile/directory
     ```

3. **Build the Docker Image**
   - Build the Docker image by specifying the custom Dockerfile using the `-f` flag:
     ```bash
     docker build -f Dockerfile.txt -t agarclimage .
     ```

4. **Run the Docker Container**
   - Once the image has been built, run the container:
     ```bash
     docker run --gpus all -it --name agarclcontainer agarclimage
     ```
   - This command will start the container with the name `agarclcontainer`. The `--gpus all` flag tells Docker to use all available GPUs on your host system for the container.

## Installing just the AgarCL Platform

Now, let's install the platform on your system (`agarclcontainer` container):

1. **Clone the AgarCL Repository**
   - Clone the repository with the `--recursive` flag to ensure all submodules are included:
     ```bash
     git clone --recursive git@github.com:AgarCL/AgarCL.git
     ```

2. **Install the Platform**
   - Change into the `AgarCL` directory:
     ```bash
     cd AgarCL
     ```

   - Run the installation command to set up the platform:
     ```bash
     python3 setup.py install --user
     ```

   - This will install the platform in your local user environment.

### Done!

You have successfully set up the AgarCL platform in a Docker container and installed the necessary dependencies. You can now start using the platform!

## Installing the AgarCL Platform and benchmarking tools

1. **Clone the AgarCL-benchmark Repository**
   - Clone the repository:
     ```bash
     git clone git@github.com:AgarCL/AgarCL-benchmark.git
     ```

2. **Navigate to the AgarCL-Benchmark Directory**
   - Change into the `AgarCL-benchmark` directory:
     ```bash
     cd AgarCL-benchmark
     ```

4. **Clone the AgarCLgit  Repository**
   - Clone the `AgarCL` repository with the `--recursive` flag to ensure all submodules are included:
     ```bash
     git clone --recursive git@github.com:AgarCL/AgarCL.git
     ```

5. **Navigate to the AgarCL Directory**
   - Change into the `AgarCL` directory:
     ```bash
     cd AgarCL
     ```

6. **Install the Platform**
   - Run the installation command to set up the platform:
     ```bash
     python3 setup.py install --user
     ```

### Done!

## macOS Installation Guide

Follow the instructions [here](https://brew.sh/) and make sure you have homebrew correctly installed and updated.

Then follow these steps to set up the AgarCL environment on macOS:

1. **Clone the repository:**
   ```bash
   git clone --recursive git@github.com:AgarCL/AgarCL.git
   ```
2. **Change into the project directory:**
   ```bash
   cd AgarCL
   ```
3. **Create a Python virtual environment:**
   ```bash
   python3 -m venv agarclenv
   ```
4. **Activate the virtual environment:**
   ```bash
   source agarclenv/bin/activate
   ```
5. **Run the installer script:**
   ```bash
   ./install.sh
   ```
6. **Install Python dependencies:**
   ```bash
   pip install -r requirements.txt
   ```
7. **Build & install the Python package:**
   ```bash
   python3 setup.py install
    ```

### Done!

## Linux Installation Guide

1. **Clone the repository:**
   ```bash
   git clone --recursive git@github.com:AgarCL/AgarCL.git
   ```
2. **Change into the project directory:**
   ```bash
   cd AgarCL
   ```
3. **Create a Python virtual environment:**
   ```bash
   python3 -m venv agarclenv
   ```
4. **Activate the virtual environment:**
   ```bash
   source agarclenv/bin/activate
   ```
5. **Run the installer script:**
   ```bash
   ./install.sh
   ```
6. **Install Python dependencies:**
   ```bash
   pip install -r requirements.txt
   ```
7. **Build & install the Python package:**
   ```bash
   python3 setup.py install
    ```
### Done!

----
Note: A graphical user interface (GUI) is required to run self-play mode or enable real-time rendering. However, a GUI is not necessary for training agents or recording and saving videos of the environment’s execution.