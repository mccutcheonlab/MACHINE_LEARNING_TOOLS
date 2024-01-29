# MACHINE_LEARNING_TOOLS
 ### <font color = "red"> This readme file is <sub>Under</sub> Construction</font>

 This repository was created through a collaboration between McCutcheon Lab at UiT and NDF at DIfE and is meant to serve as a place to store and share scripts, data, training models, etc used for tracking animals or evaluating behavioural videos via DLC, SIMBA, SLEAP and other potential machine learning tools. 


 # DeepLabCut(DLC)
 ### <font color = "green"> DLC_Installation </font>
* There are several ways to install DLC on Windows OS, e.g. installing from the scratch, using .ymal file or cloneing the repository. The process of installation is described here [DeepLabCut](https://deeplabcut.github.io/DeepLabCut/docs/installation.html) by the authors of DLC.
* Here I document my own experience of installing DLC via creating a virtual environment from scratch. 

* before starting I recommend taking a look at [CONDA_CHEATSHEET](https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdf) which includes a set of essential commands for managing virtual evnrionments.
* Moreover, take a look at this [Coding_Map](https://github.com/mccutcheonlab/MACHINE_LEARNING_TOOLS/blob/main/Miscellaneous/Coding%20MAP.pdf) to have an idea of "how everything fits together" in terms of virtual environments.

###### 1 Install [Anaconda](https://www.anaconda.com/download) on the local machine(a technical term for "your computer")

###### 2 Run the Anaconda prompt as admistrator (*especially on Windows, DLC requiers admin rights to run properly*)
 * In case the pathway shown at the terminal is /system32 , it is recommended to swtich to the root of the directory via CD command, i.e. cd c\

###### 3 Lets first check the version of Conda and if it is not the latest version you can use the command below to upgrade it
            conda update -n base -c defaults conda

###### 4 install **git** and **pip** using the commands below
            conda install -c anaconda git
            conda install pip
###### 5 Now you should have all the essentials for creating a virtual environment on you anaconda, in the command line type        
            conda create --name DeepLabCut python=3.8
<font color= "blue">*note: instead of DeepLabCut you can use any other name* </font>

###### 6 After a while the environment is created, swtich to you newly created environment using the command below:
            conda activate DeepLabCut



###### 7 Now you will notice that in your terminal, instead of ***(base) c:/*** you are located in ***(DeepLabCut) c:/***

###### 8 At this stage, you will need to install some necessary packages on your virtual environment before running DLC as follows, run one by one:
            conda install -c anaconda cudatoolkit =11.7
            pip install --upgrade tensorflow==2.10.0
            conda install -c conda-forge cudnn=8.4.1.50

<font color= "blue"> *note: after installation is done, you can check the version and validity of your installation using the command below:*</font>
                        
            conda list name_of_the_package
            e.g:
            conda list tenosrflow
###### 9 Now you can use the command below to install DLC(GUI based version, recommended)
            pip install "deeplabcut[gui,tf]

###### 10 You can install jupyter lab in your environment using the command below
            pip install jupyterlab
            or
            conda install -c conda-forge jupyterlab


<font color= "blue"> *note: you can not access DLC if you are running Jupyter Lab from the (base) environment, in another term, you have to run Jupyter lab from (DeepLabCut) environment to be able to import DLC*</font>

##### 11 Two ways to run DLC from your virtual environment:
* Use the command in the terminal to directly run the GUI:
    
            python -m deeplabcut
A new window will appear.

* Use Jupyter Lab or notebook, i.e type the command below in the terminal (DeepLabCut) c:/>

            Jupyter lab
After Jupyterlab opens up, in the first cell type the code below:

            import deeplabcut



