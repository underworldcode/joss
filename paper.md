---
title: 'Underworld2: Python geodynamics modelling for desktop, HPC and cloud.'
tags:
  - Python
  - geodynamics
  - HPC
  - FEM
  - subduction
authors:
  - name: John Mansour
    orcid: 0000-0001-5865-1664
    affiliation: 1
  - name: Louis Moresi
    orcid: 0000-0003-3685-174X
    affiliation: "3,2"
  - name: Julian Giordani 
    orcid: 0000-0003-4515-9296
    affiliation: 2
  - name: Owen Kaluza  
    orcid: 0000-0001-6303-5671
    affiliation: 1
  - name: Romain Beucher  
    orcid: 0000-0003-3891-5444
    affiliation: 2
  - name: Rebecca Farrington  
    orcid: 0000-0002-2594-6965
    affiliation: 2
  - name: Steve Quenette
    orcid: 0000-0002-0368-7341
    affiliation: 1

affiliations:
 - name: Monash eResearchCentre, Monash University, Clayton, Australia
   index: 1
 - name: School of Earth Science, The University of Melbourne, Melbourne, Australia
   index: 2
 - name: Research School of Earth Sciences, The Australian National University, Canberra, Australia
   index: 3
date: 16 August 2019
bibliography: paper.bib
---

# Summary

Underworld2 is a Python API (Application Programming Interface) which provides functionality for the modelling of long time-scale solid-Earth processes. It is designed to work (almost) seamlessly across PC, cloud and HPC infrastructure. Primarily, the API consists of a set of Python classes, instances of which will be used to construct numerical geodynamics models. The API also provides the tools required for inline analysis and data management. For the multiprocessor scalability required of high-resolution models, MPI (Message Passing Interface) is leveraged, and for performant operation all heavy computations are executed within a statically typed layer. Underworld2 continues the legacy of Underworld1 [] [] [], sharing much of the underlying mathematical approach. But Underworld2 is not a Python wrapper to Underworld1, and modelling and usage paradigms have been completely redesigned.

A primary aim of Underworld2 is to enable rapid and frictionless model development. To this end, embedded visualisation (using LavaVu) and the Jupyter Notebook environment have been embraced, allowing users to interactively build and debug their models. Underworld2 is also able to operate as a cloud based tool, with users accessing their model Notebooks via any standard web browser. Cloud based operation has been used successfully within teaching environments, and also enables our _live_ user documentation and examples. 

Underworld2 provides capacity for modelling 2- and 3-dimensional geodynamics processes, utilising a particle-in-cell finite element approach for solution to Stokes flow type configurations. In Underworld2, the finite element mesh can be static or dynamic, but it is not constrained to move in lock-step with the evolving geometry of the fluid. This hybrid approach allows for the accurate solution to the velocity problem (on the mesh) for a given material configuration, while simultaneously ensuring the accurate time advection of material interfaces and history information (using particle swarms). Templated systems are provided for solution to Stokes flow, steady state heat (or Darcy) flow, and time-dependent advection-diffusion models. 

By design, Underworld2 provides only a minimal set of flexible core functionality, and leaves _user domain_ concerns to the users themselves to construct. At the centre of this design is the _Function_ class, which aims to provide a natural interface for the description of problem dynamics. For example, the user may describe a viscosity which is piecewise constant, temperature dependent, or visco-elasto-plastic in behaviour. Simulation chronology is also fully exposed and the user is expected to explicitly specify when events should occur. This approach allows users to specify exactly their modelling requirements and more importantly provides transparency. It also prevents API bloat, helping to ensure the long term viability of the project. 

Underworld2 is utilised by the UWGeodynamics Python module [@Rbeucher], which provides a more structured interface to geodynamics model construction. It has enabled numerous recent publications, include [], [], and [].  

# Acknowledgements

Underworld development was financially supported by AuScope and the Australian Government via the National Collaborative Research Infrastructure Strategy (NCRIS): (auscope.org.au). Additional funding for specific improvements and additional functionality has come from the Australian Research Council (http://www.arc.gov.au). The Python toolkit was funded by the NeCTAR eresearch_tools program. Underworld was originally developed in collaboration with the Victorian Partnership for Advanced Computing.


