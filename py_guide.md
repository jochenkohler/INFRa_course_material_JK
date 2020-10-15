# Getting started with Python

## Guide to install Python related software for the course.

If you find mistakes/typos or links that do no longer function, please contact: 

Jorge Mendoza (jorge.m.espinosa@ntnu.no)  
NTNU - PhD student

### Install Python 3.7

First, make sure that you have python 3.7 installed. To verify that, open a terminal window. You may do this:

+ MacOS: open spotlight with the shortcut Cmd + spacebar, and type-in: *terminal*. Then, hit enter to open the terminal.
+ Windows: One of the following two options: 
    - Windows+R, then type-in *cmd* and press enter.
    - Start >> Program Files >> Accessories >> Command Prompt

Once you have a terminal window opened, type the following command (note that the dollar symbol indicates beginning of command, but should not be typed in the command window):
```
$ python -V
```
If you need to install Python 3.7 in your computer, here are some guides:
+ [NTNU guide](https://innsida.ntnu.no/wiki/-/wiki/English/Installing+Python#section-Installing+Python-Install+the+latest+version+of+Python) (for Windows, MacOS, and LINUX)
+ [For MacOS](https://opensource.com/article/19/5/python-3-default-mac) (in case you find it better/easier than the NTNU guide)

### Install Anaconda
Now install Anaconda.  This depends on your operating system:

#### MacOS

Make sure you are working on a zsh terminal. Type the following command:
```
$ chsh -s /bin/zsh
```
And restart your terminal. It should say -- ~ -- -zsh on top. 

Now install Anaconda. Try the instructions in this [link](https://towardsdatascience.com/how-to-successfully-install-anaconda-on-a-mac-and-actually-get-it-to-work-53ce18025f97) first. If you have trouble doing it this way, you may look at this other [link](https://docs.anaconda.com/anaconda/install/mac-os/#macos-graphical-install). 
After you have installed it, run this command: 
```
$ conda init zsh
```

#### Windows: 
Use this [link](https://docs.anaconda.com/anaconda/install/windows/).

### Verify Spyder version

To check installed Spyder version:
```
$ conda list Spyder$
```
If Spyder is correctly installed, you should see the following output:
```
# packages in environment at /Users/usrname/anaconda3/envs/tktpy:
#
# Name                    Version                   Build  Channel
spyder                    4.1.3            py37hc8dfbb8_0    conda-forge
```

If Spyder is not installed:
```
$ conda install -y spyder
```
To update Spyder to the latest version (20.08.20 is 4.1.3):
```
$ conda update -y spyder
```

### Python packages

Create a conda environment called tktpy: 
```
$ conda create --name tktpy python=3.7
```

Once the process is finished, check that it has been successfully created:
```
$ conda info --envs
```

It should show at least an environment called base (with a * next to it) and another called tktpy. The * means that the current environment is base. We need to activate the environment we want to work at. For that, type the following:
```
$ conda activate tktpy
```

Next, you need to install the course requirements. These are the python packages that we will use during the course. They are stored in a file called 'tktreq.txt'. To download the file, type:
```
$ curl -OL https://raw.githubusercontent.com/Jorgemendozaesp/TKT4196-CourseMaterial/master/tktreq.txt
```

To install them, type the following command:
```
$ pip install -r tktreq.txt 
```

### Jupyter

Jupyter notebooks are created for pedagogic purpose. You can use Jupyter Notebooks or Jupyter-lab to view/edit notebooks. To use widgets (interactive boxes) follow these instructions:
To install jupyter-lab (assuming that conda is installed): 
```
$ conda install -y jupyter jupyterlab nodejs
```

Then, install the required widget extensions with the following commands:
```
$ pip install ipywidgets
$ jupyter nbextension enable --py widgetsnbextension
$ jupyter labextension install @jupyter-widgets/jupyterlab-manager
```
