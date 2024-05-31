# First Steps

## Installation

### Using an Anaconda environment and pip

1. Install Anaconda (visit: https://www.anaconda.com/products/individual)
2. Create an analysis environment with the following command:

```bash
conda create -n pydg_analysis python=3.11
```

Only Python (and `pip`) are needed, the rest is installed via the package's dependencies.

3. Activate the environment with:

```bash
conda activate pydg_analysis
```

This steps should be done every time before you start the analysis.

4. Install Pynamic Gain via pip:

```bash
pip install pynamicgain
```

This will install the package and all dependencies. Please do not worry, the initial installation might take a little longer, as all dependencies are installed.

After this you can test the installation with the following command:

```bash
pydg_help
```

--- 

## First usage

For the first usage, you need to create a new setup. This setup will be used for the generation of input files and the analyses.
Currently, we need to coordinate the setup ids, please talk to us before creating a new setup. 

### Create a new setup

1. Initiate the setup with the following command and follow the instructions there:

```bash
pydg_new_setup
```

Please Note, that on the very first occasion, the program might take a little longer to start, as all imports must be loaded. This is a one-time thing.

2. Follow the instructions in the command line interface.

![new_setup_cli](./_images/pynamicgain_new_setup.svg)

It would be nice, if you could send a short email with the setup number, a short description of the setup (and the setup file) after the setup is created to your friendly neighbourhood Goettingen cooperators. This way, we can keep track of the setups and their numbers. Furthermore the setup files can be stored in a different branch of the repository.

As the setup files contain the running seed numbers, it might be advisable to save (backup) them locally from time to time.  
(You can also send us an copy via email to store it online.)

---

Now you are ready to start the input generation or the analyses. Please see the [Usage](./usage.md) for more information.