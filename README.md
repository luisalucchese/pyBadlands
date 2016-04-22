pyBadlands - the Python version of Badlands
=====

<div align="center">
    <img width=500 src="https://github.com/badlands-model/Badlands-doc/blob/master/figures/sketch.png" alt="sketch Badlands" title="sketch of Badlands range of models."</img>
</div>
_A schematic of 2D landscape evolution model illustrating the main variables and forces simulated with Badlands: z is the surface elevation, r refers to rainfall, sl to sea-level fluctuations, f to the flexural isostasy and u to geodynamic forces (from [**Salles & Hardiman, 2016**](http://dx.doi.org/10.1016/j.cageo.2016.03.011))._

## Overview

**Ba**sin an**d** **Lan**dscape **D**ynamic**s** (**Badlands**) is a parallel TIN-based landscape evolution model, built to simulate topography development at various space and time scales. The model is capable of simulating hillslope processes (**linear** diffusion), fluvial incision (*'modified'* **Stream Power Law**, **Transport Capacity Law** both for sediment  erosion/transport/deposition), spatially and temporally varying geodynamic (horizontal + vertical displacements) and climatic forces which can be used to simulate changes in base level, as well as effects of climate changes or sea-level fluctuations. The model uses  [**gFlex**](https://github.com/awickert/gFlex) package which is designed to solve elastic plate flexure for applications to Earth's lithosphere.

## Getting started

The latest pyBadlands version is the one that’s in our Github [repository](https://github.com/badlands-model/pyBadlands). Get it using this shell command, which requires Git:
* `git clone https://github.com/badlands-model/pyBadlands.git`

However, the easiest way to get started is with the [Docker container](https://hub.docker.com/u/badlandsmodel/) using [Kitematic](https://docs.docker.com/kitematic/userguide/). Once **Kitematic** is installed on your computer, open it and look for **pybadlands-demo** via the *search* menu.

If you want to install it yourself, these 2 Dockerfiles ([**dependencies**](https://github.com/badlands-model/pyBadlands-Dependencies-Docker/blob/master/Dockerfile) & [**code**](https://github.com/badlands-model/pyBadlands-Docker-Demo/blob/master/Dockerfile)) is the best documentation of the required packages.

## The specs...

The model is based on the following characteristics: 
* The finite volume approach from [**Tucker et al. (2001)**](http://www.sciencedirect.com/science/article/pii/S0098300400001345) based on the dual Delaunay-Voronoi framework is used to solve the continuity equation explicitly, 
* Node ordering is perform efficiently based on the work from [**Braun & Willett (2013)**](http://www.sciencedirect.com/science/article/pii/S0169555X12004618),
* 3D surface deformations using the node refinement technique proposed by [Thieulot et al., 2014](http://onlinelibrary.wiley.com/doi/10.1002/2014GC005490/abstract;jsessionid=48A885F79A40B1E3E76AFC1BEAA2B238.f03t03). 

A set of functions for _pre_ & _post_-processing for **Badlands** input and output are available in a github [**Companion**](https://github.com/badlands-model/pyBadlands-Companion) repository which is already shiped with the Badlands docker container.

## Community driven

This program is free software: you can redistribute it and/or modify it under the terms of the GNU Lesser General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU Lesser General Public License for more details.

You should have received a copy of the GNU Lesser General Public License along with this program.  If not, see <http://www.gnu.org/licenses/lgpl-3.0.en.html>.

The code is conceived as an open-source project, and is an ideal tool for both **Research** and **Learning** purposes.

### EarthByte software 

**Badlands** is part of the suite of software developed by the EarthByte [group](http://www.earthbyte.org/category/resources/).

### Reporting  

If you come accross a bug or if you need some help compiling or using the code [drop us a line](tristan.salles@sydney.edu.au).

## Hands-on examples

A compilation of notebooks with examples are proposed to give you a quick feeling of what could be done with the code. Testing models:

+ delta evolution under sea-level fluctuation [nbviewer](http://nbviewer.jupyter.org/github/badlands-model/pyBadlands/blob/master/Examples/delta/delta.ipynb)
+ impact of climate on mountain dynamic [nbviewer](http://nbviewer.jupyter.org/github/badlands-model/pyBadlands/blob/master/Examples/mountain/mountain.ipynb)
+ basin filling associated to a strike-slip fault system [nbviewer](http://nbviewer.jupyter.org/github/badlands-model/pyBadlands/blob/master/Examples/strikeslip/strike-slip.ipynb)
+ infilling of a crater-type topography [nbviewer](http://nbviewer.jupyter.org/github/badlands-model/pyBadlands/blob/master/Examples/crater/crater.ipynb)
+ flexural response due to loading and unloading under variable elastic thickness [nbviewer](http://nbviewer.jupyter.org/github/badlands-model/pyBadlands/blob/master/Examples/flexure/flexure.ipynb)
+ quick setup of real topography/bathymetry model using etopo1 [nbviewer](http://nbviewer.jupyter.org/github/badlands-model/pyBadlands/blob/master/Examples/etopo/etopo.ipynb)

Some documentation related to the physics & assumptions of the model can be found in:

**Salles, T. & Hardiman, L.: [Badlands: An open-source, flexible and parallel framework to study landscape dynamics](http://dx.doi.org/10.1016/j.cageo.2016.03.011), Computers & Geosciences, 91, 77-89, doi:10.1016/j.cageo.2016.03.011, 2016.**

When you use **Badlands**, please cite the above paper.
