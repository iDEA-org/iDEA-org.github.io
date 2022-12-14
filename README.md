# <img src="docs/logo.png" alt="" width="70"/> iDEA - The interacting Dynamic Electrons Approach

Exploring exact and approximate methods for many-electron quantum mechanics.

![pip](https://img.shields.io/pypi/v/iDEA-latest)
![tag](https://img.shields.io/github/v/tag/iDEA-org/iDEA)
[![Documentation Status](https://readthedocs.org/projects/idea-interacting-dynamic-electrons-approach/badge/?version=latest)](https://idea-interacting-dynamic-electrons-approach.readthedocs.io/en/latest/?badge=latest)
![Issues](https://img.shields.io/github/issues/iDEA-org/iDEA)
![Pull Requests](https://img.shields.io/github/issues-pr/iDEA-org/iDEA)

**iDEA (interacting Dynamic Electrons Approach) is a high-performance, user friendly, free software framework in python for state-of-the-art research, experiments, testing and education in many-body quantum physics with a focus on reproducibility, interactivity and simplicity.**

[Homepage](https://idea-org.github.io/)  

[View on GitHub](https://github.com/iDEA-org/iDEA)

![demo](demo.gif)

## Installation

### User

To install the [latest version of the iDEA code](https://pypi.org/project/iDEA-latest/):

`pip install iDEA-latest`

To add iDEA to your poetry environment:

`poetry add iDEA-latest`

### Developer

If you would like to develop iDEA, first fork this git repository, and then clone from there.

Add the upstream repository: `git remote add upstream https://github.com/iDEA-org/iDEA.git`

And then install locally: `python setup.py install`

## Documentation

For full details of usage please see our [tutorial](https://github.com/iDEA-org/iDEA/blob/master/tutorial/tutorial.ipynb). The full API documentation is available at [readthedocs](https://idea-interacting-dynamic-electrons-approach.readthedocs.io/en/latest/).

## Features

Some of iDEA's features:
- Exact solution of the many-electron problem by solving the static and time-dependent Schrödinger equation, including exact exchange and correlation.
- Exact solutions which approach the degree of exchange and correlation in realistic systems.
- Free choice of external potential that may be time-dependent, on an arbitrarilty dense spatial grid, for any number of electron with any spin configuration.
- Implementation of various approximate methods (established and novel) for comparison, including:
    - Non-interacting electrons
    - Hartree theory
    - Restricted and unrestricted Hartree-Fock
    - The Local Density Approximation (LDA)
    - Hybrid functionals
- Implementation of all common observables.
- Reverse-engineering to solve potential inversion, from exact Kohn-Sham DFT and beyond.
- Fully parallelised using OpenBLAS.
- Fully parallelised for all cuda supporting GPUS.

## Example

In order to solve the Schrödinger equation for the two electron atom for the ground-state charge density and total energy:

```
import iDEA
system = iDEA.system.systems.atom
ground_state = iDEA.methods.interacting.solve(system, k=0)
n = iDEA.observables.density(system, state=ground_state)
E = ground_state.energy

import matplotlib.pyplot as plt
print(E)
plt.plot(system.x, n, 'k-')
plt.show()
```

## Tutorial

We provide a [tutorial](https://github.com/iDEA-org/iDEA/blob/master/tutorial/tutorial.ipynb) where you can learn how to use the iDEA code in your research and teaching projects.

## Papers You Can Reproduce With iDEA

1. "Advantageous nearsightedness of many-body perturbation theory contrasted with Kohn-Sham density functional theory", J. Wetherell, M. J. P. Hodgson, L. Talirz, and R. W. Godby, Physical Review B 99 045129 (2019).
[paper](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.99.045129), [reprint](https://jackwetherell.github.io/files/nearsightedness.pdf), [preprint](https://arxiv.org/pdf/1812.02661.pdf), [code](https://github.com/JackWetherell/advantageous-nearsightedness).

More coming soon...

The development and applications of the iDEA code from 2010 to 2021 is documented [here](https://www-users.york.ac.uk/~rwg3/idea.html).

## Teaching

iDEA can also be used to create teaching content, visualisations and expositions> For example, see the following [YouTube video created using iDEA](https://www.youtube.com/watch?v=JaSVguMFA-M&ab_channel=JackWetherell).

iDEA was used to create teaching content for the [Density Functional Theory MOOC on Coursera](https://www.coursera.org/learn/density-functional-theory).

## Developers

<img src="docs/dev.png" alt="" width="500"/>

## Contributors

We thank all of the developers, PhD students, masters students, summer project interns and researchers for thier key contributions to iDEA:

Sean Adamson, Jacob Chapman, Thomas Durrant, Razak Elmaslmane, Mike Entwistle, Rex Godby, Matt Hodgson, Piers Lillystone, Aaron Long, Robbie Oliver, James Ramsden, Ewan Richardson, Matthew Smith, Leopold Talirz and Jack Wetherell. 

## Getting Involved

To get involved:
- Raising issues and pull requests here is greatly appreciated!
- We can add any papers that can be fully reproduced by iDEA to our dedicated page by sending your open access paper to jack.wetherell@gmail.com.
- We provide a [template](https://github.com/iDEA-org/iDEA-project-template) to get you started!

## Dependencies

iDEA supports `python 3.8+` along with the following dependences:
```
numpy >= "1.22.3"
scipy >= "1.8.0"
matplotlib >= "3.5.1"
jupyterlab >= "3.3.2"
tqdm >= "4.64.0"
```

<img src="docs/logos.png" alt="" width="200"/>
