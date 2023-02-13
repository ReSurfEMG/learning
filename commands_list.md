## This is a list of the commands that will be used dunring the workshop

# Clone ReSurfEMG

`git clone https://github.com/ReSurfEMG/ReSurfEMG.git`

# Clone ReSurfEMG-dashboard

`git clone https://github.com/ReSurfEMG/ReSurfEMG-dashboard.git`

# Clone ridethewave

`git clone https://github.com/ReSurfEMG/ridethewave.git`

# Create a new branch on `ridethewave`:

`git checkout -b "yourname/your-branch-name"`

# deactivate conda environment

`conda deactivate env-name`

# activate ReSurfEMG environment

`conda activate you_workshop`

# generate synthetic data

`python -m resurfemg synth -i ./synth_data -o ./output_data -N 5`

# activate ReSurfEMG-dashboard environment

`conda activate dashboard`

# start dashboard

`python index.py`