---
layout: default
title: Academic Research Profile
tags: [research, phd, masters]
comments: false
permalink: /research/
---

## Academic Research ##

My publication list is available [here](https://scholar.google.com.au/citations?user=UWC2tnAAAAAJ&hl=en).

### PhD ###

My research involved the use of [Diffusion MRI](https://en.wikipedia.org/wiki/Diffusion_MRI) to assist in the identification and characterization of prostate cancer.  I worked on Monte Carlo simulations of diffusion in virtual cellular environments to mimic prostate tissue.  Also did a lot of modeling analysis using regression methods on Diffusion MRI signal data.  I used MATLAB for most image analysis, [MevisLab](https://www.mevislab.de/) to import and crop MRI DICOM data, and Python for both scientific and general purpose applications. 

A lot of my research involved the analysis of whole organs and tissue samples from prostates extracted from surgery via prostatectomy due to prostate cancer diagnosis.  We imaged the whole organ in a 9.4 T small animal scanner before and after fixation (see this paper) to get the high resolution organ images as seen below.  We also analyzed high resolution MR images on a 16.4 T spectrometer on prostate core samples taken from pathology after dissection.  These images had even higher resolution (~ 40 micron voxel size) to allow for diffusion analysis at the cellular level, with an example image seen on the [front page](/).  I also was involved with in vivo analysis for both prostate cancer and lymphedema present in the forearm after breast cancer diagnosis and treatment.

### Master's ###

In 2012, I completed a Masters of Science with the [Astrophotonics](http://sydney.edu.au/science/physics/research/sifa/astrophotonics/) group in the [Sydney Institute for Astronomy](https://sydney.edu.au/science/physics/sifa/), which is part of the [School of Physics](https://sydney.edu.au/science/physics/) at the University of Sydney.  The bulk of my work consisted of the design of path-length matched optical waveguides, which were fabricated on a single glass chip using a high-powered laser to form an optical interferometer.  This interferometer was tested on the [Anglo-Australian Telescope (AAT)](http://www.aao.gov.au/) and successful interferometric fringe measurements of a few stars were made.  We published a paper based on our results [here](http://onlinelibrary.wiley.com/doi/10.1111/j.1365-2966.2012.21997.x/full) (or on arxiv [here](http://arxiv.org/abs/1210.0603)).

My Masters thesis is available online via the University of Sydney’s eScholarship Repository [here](http://hdl.handle.net/2123/10282), however, I did publish a paper on the bulk of my thesis work [here](http://www.opticsinfobase.org/ao/abstract.cfm?uri=ao-51-27-6489) ([arxiv](https://arxiv.org/ftp/arxiv/papers/1209/1209.5144.pdf)).  My waveguide design code for this paper (and my thesis) was written in Python and contains all of the functions I wrote to path length match the optical waveguides, as well as verify their spatial separation, calculate expected power loss, provide machine coordinates to the fabrication system, and display the waveguides in 3D using mayavi2, among others.  You can download this [code](https://github.com/diffusioned/Python-Code/blob/master/OpticalWaveguideCreation.py) freely on [my github](https://github.com/diffusioned), and all functions are contained in one file, which is both a strength and weakness, as is my penchant for long, explicit variable names.  It could use a lot of work and a simple minimization or line search algorithm would speed the length search portion considerably, but at that time, I didn’t have much experience with that sort of thing.  If any of this Python code helps your work out, feel free to reference my [paper](http://www.opticsinfobase.org/ao/abstract.cfm?uri=ao-51-27-6489).