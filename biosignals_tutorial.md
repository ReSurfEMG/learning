# Biosignals tutorial :stethoscope:


This tutorial will cover multiple topics:

1. Version control and GIT: and hands-on intro
2. Command line from ReSurfEMG: a hands on exercise in synthetic data creation
3. The ReSurfEMG dashboard: installing and working with EMG data
4. The ReSurfEMG reseacher interface: open science and open code
5. Alternatives to ReSurfEMG
6. Software sustainability and best practices for respiratory EMG data

To get the most from this tutorial you will need to:

1. To bring your laptop
2. Have an integrated development environment (IDE) e.g. VS Code ([download](https://code.visualstudio.com/Download)), already installed on your laptop.
3. If you do not already have conda and/or mamba on your machine, get Anaconda/conda([instructions](https://docs.anaconda.com/anaconda/install/))
4. Have Git on your laptop [recommended download](https://git-scm.com/)
5. Have a Python 3.8 or above ( if you need to get look [here](https://www.python.org/downloads/) )
6. Sign up for [Github](https://github.com/) if you do not have an account. This is where the repository and tutorial material are. 
7. Clone the [ReSurfEMG/ReSurfEMG](https://github.com/ReSurfEMG/ReSurfEMG) repository onto your machine because the first time you clone a repository will take longer than ever again if you have not been using Git. For this reason we ask you to clone a repo before arriving. You may need to set up git as below:

    Setup git: 

        git config --global user.name <your username>

        git config --global user.email <your valid email>

8. Build the code environment in the workshop.yml by exiting any existing environment, then running 
        ```conda env create -f workshop.yml ```

9. Clone the [dashboard](https://github.com/ReSurfEMG/ReSurfEMG-dashboard)

10. Build the dashboard environment after you are inside the dashboard repo with the environment.yml by exiting any existing environment, then running 
        ```conda env create -f environment.yml ```