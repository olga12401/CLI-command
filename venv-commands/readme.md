##  Install VENV

To install a virtual environment with Python 3.11 on WSL (Windows Subsystem for Linux) using Ubuntu, follow these steps. This guide assumes you have WSL set up and Ubuntu installed. If Python 3.11 is not already installed, we'll cover its installation as well.

### Step 1: Update and Upgrade Packages

First, make sure your package list and the system itself are up to date. Open your Ubuntu terminal in WSL and execute:

```

sudo apt update && sudo apt upgrade -y
```

###  Step 2: Install Python 3.11

Before proceeding, check if Python 3.11 is available in your Ubuntu repositories. As of my last update, Python 3.11 might not be available in the default Ubuntu repositories for some versions of Ubuntu. You might need to add a PPA (Personal Package Archive) or install Python 3.11 manually from source. Here, I'll show you a generic way to check for Python 3.11 and install it.

Check for Python 3.11:

```
apt search python3.11

```

If Python 3.11 is available, you can install it using:

```
sudo apt install python3.11 -y
```

If Python 3.11 is not available in your repository, consider adding a PPA or installing from source. Installing from source is more complex and requires building Python on your machine.

###  Step 3: Install pip

Ensure pip is installed for Python 3.11. If it's not installed, you can install it by executing:

```
sudo apt install python3-pip -y

```
####  Step 4: Install Virtual Environment Package

Python3 includes the venv module by default to create virtual environments. If you prefer virtualenv, you can install it using pip:

```
pip install virtualenv

```

### Step 5: Create a Virtual Environment

Navigate to the directory where you want to create the virtual environment and execute:

```
python3.11 -m venv myenv

```

Replace myenv with your desired environment name.

###  Step 6: Activate the Virtual Environment

To activate the virtual environment, use:

```
source myenv/bin/activate
```

When the virtual environment is activated, your terminal prompt will change to show the name of the activated environment.

###  Step 7: Deactivate the Virtual Environment

To exit the virtual environment, simply run:

```
deactivate
```

## Venv using python 3.11.8

To install Python 3.11.8 and create a virtual environment on Ubuntu running on Windows Subsystem for Linux (WSL), you can follow these steps. The steps involve installing Python, verifying the installation, and then setting up a virtual environment.

###  Step 1: Update and Upgrade Package List

First, ensure your package list and installed packages are updated.

```
sudo apt update
sudo apt upgrade
```

###  Step 2: Install Required Dependencies

Before installing Python 3.11.8, you should ensure that all the dependencies are satisfied.

```
sudo apt install -y build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev curl libbz2-dev
```

###  Step 3: Download Python 3.11.8

You can download Python 3.11.8 from the official Python website. It's a good practice to check the latest version available on the Python official website to get the correct version number and download link.

```
curl -O https://www.python.org/ftp/python/3.11.8/Python-3.11.8.tar.xz
```

###  Step 4: Extract the Tarball

After downloading, extract the tarball and navigate into the directory.

```
tar -xf Python-3.11.8.tar.xz
cd Python-3.11.8
```

###  Step 5: Configure and Install Python 3.11.8

Configure the Python source code and start the installation process.

```
./configure --enable-optimizations
make -j $(nproc)
sudo make altinstall
```

Using make altinstall instead of make install prevents replacing the default python3 binary file, thus avoiding potential issues with system scripts that rely on Python 2.7.

###  Step 6: Verify Installation

Ensure Python 3.11.8 is correctly installed by checking its version.

```
python3.11 --version
```

### Step 7: Create a Virtual Environment

Now that Python 3.11.8 is installed, you can create a virtual environment. First, choose or create a directory where you want to place your virtual environment. Then, create the virtual environment using the following command.

```
python3.11 -m venv myenv
```

Replace myenv with your desired name for the virtual environment.

### Step 8: Activate the Virtual Environment

To start using the virtual environment, you need to activate it.

```
source myenv/bin/activate
```

When the virtual environment is activated, you'll see its name in the terminal prompt. Now, you're in a separate Python environment where you can install packages without affecting the global Python installation.

Deactivate Virtual Environment
To stop using the virtual environment and go back to the global Python environment, use the following command:

```
deactivate
```

This process allows you to manage Python packages and dependencies more effectively, especially when working on multiple Python projects.
