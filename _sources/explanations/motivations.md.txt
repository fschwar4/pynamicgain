# Motivations

This section provides additional information about the motivation about certain development decisions.
It is not necessary to read this section to use the package, but it might help to understand the reasoning behind certain decisions.

It is not ordered and also meant to be a collection of notes to remind us of the reasons for certain decisions.

## Setup Management

Ideally there would be a central (online) database to manage setups, keep track of setup IDs and ideally provide an automatic way to create new setups. However, this is not possible for us at the moment. So we hope that we can all work together to keep track of the setup ids in a cooperative way.  
Please send a short email with the setup number, a short description of the setup (and the setup file) to your friendly neighbourhood Goettingen cooperators after creating the setup.

## Seeds

Currently, each setup will have a predefined region of the BitGenerator's seed space. This way we can ensure reproducibility and no double use of seeds.  
Each setup will have one million seeds, which should be more than enough.

### Seed estimation

- 7 seeds per cell
- 15 cells on a good day
- 5 good days per week (very motivated PhD student)
- 52 weeks per year (extremely motivated PhD student)
- for 5 years (it takes what it takes)

This gives us 27300 seeds per year and **136500 seeds** for 5 years.

To be on the safe side, each setup gets a list of one million seeds (136500 < 1e6).

**Master Seed to generate the seed sequence via the PCG64DXSM bit generator: 121912940104681416.**


## ABF Files

The [pCLAMP setups by Molecular Devices](https://www.moleculardevices.com/products/axon-patch-clamp-system) uses the [ABF file format](https://www.moleculardevices.com/sites/default/files/en/assets/user-guide/dd/cns/axon-binary-file-format-v2-0-6.pdf).
For reading and writing ABF files, we rely on the [`pyabf`](https://pypi.org/project/pyabf) package – thanks!


## Setup Sample Rate

The sample rate for the input (stimulation) and the output (patch readout) is assumed to be identical.  
If there is a setup where this is not the case, please let us know.


## Units

The stimulation units are currently set/fixed to 'pA' by writing this into the ABF file.

For easier usage, the correlation time of the OU process is read in milliseconds.
However, it will be internally converted to seconds.


## Analysis

Currently the analysis is done sweep-wise.

## Random Number Generation

The random number generation is done with the `PCG64DXSM` bit generator from the `numpy.random` package.
See the [numpy documentation](https://numpy.org/doc/stable/reference/random/bit_generators/pcg64dxsm.html) for more information.
See also [the other resources there](https://numpy.org/doc/stable/reference/random/upgrading-pcg64.html).

TODO: Add more information about the random number generation.

---

## Program Structure

TODO: ADD MORE INFORMATION ABOUT THE PROGRAM STRUCTURE

![Program Structure](./_images/pynamicgain_classgraph.svg)

![Program Structure](./_images/pynamicgain_package.svg)
