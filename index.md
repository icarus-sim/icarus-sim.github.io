---
layout: index
title: Icarus
titlehead: Icarus - ICN Caching Simulator  
tagline: Caching simulator for Information Centric Networking (ICN)
---

Icarus is a Python-based simulator for evaluating caching performance in Information Centric Networking (ICN).

Icarus has been designed to be easy to use and very extensible.

### Download
You can download a stable release in a zip or tar.gz format using the links below.

**Latest version:**

 * Version 0.4.0: \[[zip](https://github.com/icarus-sim/icarus/archive/v0.4.0.zip)\] \[[tar.gz](https://github.com/icarus-sim/icarus/archive/v0.4.0.tar.gz)\]

**Older versions:**

 * Version 0.3.0: \[[zip](https://github.com/icarus-sim/icarus/archive/v0.3.0.zip)\] \[[tar.gz](https://github.com/icarus-sim/icarus/archive/v0.3.0.tar.gz)\]
 * Version 0.2.1: \[[zip](https://github.com/icarus-sim/icarus/archive/v0.2.1.zip)\] \[[tar.gz](https://github.com/icarus-sim/icarus/archive/v0.2.1.tar.gz)\]
 * Version 0.2.0: \[[zip](https://github.com/icarus-sim/icarus/archive/v0.2.zip)\] \[[tar.gz](https://github.com/icarus-sim/icarus/archive/v0.2.tar.gz)\]
 * Version 0.1.1: \[[zip](https://github.com/icarus-sim/icarus/archive/v0.1.1.zip)\] \[[tar.gz](https://github.com/icarus-sim/icarus/archive/v0.1.1.tar.gz)\]
 * Version 0.1.0: \[[zip](https://github.com/icarus-sim/icarus/archive/v0.1.zip)\] \[[tar.gz](https://github.com/icarus-sim/icarus/archive/v0.1.tar.gz)\]

You can also get the development branch from the Github repository using Git. Just open a shell, `cd` to the directory where you want to download the simulator and type:

    $ git clone https://github.com/icarus-sim/icarus.git

### Configuration
Before using the simulator, you need to install all required dependencies.

If you use Ubuntu (version 13.10+) you can run the script `ubuntusetup.sh` located in the `scripts` folder which will take of installing all the required dependencies.
To run it, execute the following commands:

    $ cd <YOUR ICARUS FOLDER>
    $ sh scripts/ubuntusetup.sh

The script, after being launched, will ask you for superuser password.

Otherwise, have a look at the `README.md` file, which explains how to configure your machine and install all required dependencies for other operating systems.


### Usage

#### Run simulations
To use Icarus with the currently implemented topologies and models of caching policies and strategies you need to do the following.

First, create a configuration file with all the desired parameters of your simulation. You can modify the file `config.py`, which is a well documented example configuration. You can even use the configuration file as it is just to get started. Alternatively, have a look at the `examples` folder which contains examples of configuration files for various uses.

Second, run Icarus by running the script `icarus.py` using the following syntax

    $ python icarus.py --results RESULTS_FILE CONF_FILE

where:

 * `RESULTS_FILE` is the [pickle](http://docs.python.org/3/library/pickle.html) file in which results will be saved,
 * `CONF_FILE` is the configuration file

Example usage could be:

    $ python icarus.py --results results.pickle config.py

After saved results in pickle format you can extract results in a human readable format
using the `printresults.py` script from the `scripts` folder. Example usage could be:

    $ python scripts/printresults.py results.pickle > results.txt

Icarus also provides a set of helper functions for plotting results. Have a look at the `examples`
folder for plot examples.

By executing the steps illustrated above it is possible to run simulations using the
topologies, cache eviction policies, strategies and result collectors readily available on
Icarus. Icarus makes it easy to implement new models to use in simulations.

To implement new models, please refer to the description of the simulator 
provided in this paper:

L.Saino, I. Psaras and G. Pavlou, Icarus: a Caching Simulator for Information Centric
Networking (ICN), in Proc. of SIMUTOOLS'14, Lisbon, Portugal, March 2014.
\[[PDF](http://www.ee.ucl.ac.uk/~lsaino/publications/icarus-simutools14.pdf)\],
\[[Slides](http://www.ee.ucl.ac.uk/~lsaino/publications/icarus-simutools14-slides.pdf)\],
\[[BibTex](http://www.ee.ucl.ac.uk/~lsaino/publications/icarus-simutools14.bib)\]

Otherwise, please browse the source code. It is very well documented and easy to
understand.

#### Modelling tools
Icarus provides utilities for modelling the performance of caches and
work with traffic traces. The code is included in the `icarus.tools` package.
These tools are described in detail in [this paper](http://www.ee.ucl.ac.uk/~lsaino/publications/icarus-simutools14.pdf).

### Documentation
If you desire further information about Icarus, you can find it in the following places:

 * In this ([pdf](http://www.ee.ucl.ac.uk/~lsaino/publications/icarus-simutools14.pdf), [slides](http://www.ee.ucl.ac.uk/~lsaino/publications/icarus-simutools14-slides.pdf)),
   which describes the overall architecture of the Icarus simulator, the motivations for its design, 
   the models implemented and shows some snippets of codes on how to use the modelling tools.
 * In the [API reference](http://icarus-sim.github.io/doc/), which documents all packages, modules, classes, methods
   and functions included in the Icarus simulator.
 * In the [source code](https://www.github.com/icarus-sim/icarus), which is well organized and thoroughly documented.

### Citing
If you use Icarus for your paper, please refer to the following publication:

    @inproceedings{icarus-simutools14,
       author = {Saino, Lorenzo and Psaras, Ioannis and Pavlou, George},
       title = {Icarus: a Caching Simulator for Information Centric Networking (ICN)},
       booktitle = {Proceedings of the 7th International ICST Conference on Simulation Tools and Techniques},
       series = {SIMUTOOLS '14},
       year = {2014},
       location = {Lisbon, Portugal},
       numpages = {10},
       publisher = {ICST},
       address = {ICST, Brussels, Belgium, Belgium},
    }

### Reproduce hash-routing results
The Icarus simulator can be used to reproduce the results and plot the graphs presented in the paper:

L.Saino, I. Psaras and G. Pavlou, Hash-routing Schemes for Information Centric Networking,
in *Proc. of the 3rd ACM SIGCOMM workshop on Information Centric Networking (ICN'13)*, Hong Kong, China, August 2013.
[\[PDF\]](http://www.ee.ucl.ac.uk/~lsaino/publications/hashrouting-icn13.pdf),
[\[BibTex\]](http://www.ee.ucl.ac.uk/~lsaino/publications/hashrouting-icn13.bib)

All the code, data and documentation required is made available in the [icarus-sim/hashrouting-icn13-results](http://github.com/icarus-sim/hashrouting-icn13-results) repository.

### License
Icarus is licensed under the terms of the [GNU GPLv2 license](http://www.gnu.org/licenses/gpl-2.0.html).

### Contacts
For further information about the Icarus simulator, please contact [Lorenzo Saino](http://www.ee.ucl.ac.uk/~lsaino).

### Acknowledgments
This work has been funded by the EU-Japan initiative, under EU FP7 grant agreement no. 608518 and NICT contract no. 167 ([GreenICN](http://www.greenicn.org/)), and by the EU FP7 grant agreement ICT-248784 ([COMET](http://www.comet-project.org/)).