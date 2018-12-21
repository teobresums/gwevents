---
layout: page
title: About
permalink: /about/
---

`TEOBResumS` is a state-of-art effective-one-body (EOB) model for
generating dynamics and waveforms of black holes and neutron star
binaries in general relativity. Main feats

 * Pade'-resummed point-mass conservative dynamics and informed by numerical relativity (NR) simulations of binary black holes at (effective) fifth post-Newtonian (PN) order
 * Resummed [Damour-Iyer-Nagar](http://inspirehep.net/record/802497) waveform 
 * Spin-orbit and spin-spin effects blended together by the centrifugal EOB radius
 * NR-based phenomenological description of the postmerger waveform for binary black holes
 * Tidal gravitoelectric and gravitomagnetic effects obtained with blending and resummation of PN and gravitational self-force (GSF) information
 * Equation of state - dependent, quadratic-in-spin, self-spin effects at next-to-next-to-leading PN order
 * Multipolar waveform and fluxes 
 
You can find a technical description of the model [here](https://inspirehep.net/record/1676430). As for the name, *T* stands for tides, *Resum* indicate the use of analytical resummation techniques, and *S* for spins. 

## Can I try?

Yes, `TEOBResumS` code is publicly available !

Start by cloning the code repo

```
git clone git@bitbucket.org:eob_ihes/teobresums.git
```

and taking a look at the [Wiki](https://bitbucket.org/eob_ihes/teobresums/wiki/Home) there. There are examples and parfiles to start with. You want to use the code version tagged as `v1.0`.

Quick start with the binary neutron star event [GW170817](https://www.gw-openscience.org/events/GW170817/):

```
$ cd /PATH/TO/teobresums/C
$ export TEOBRESUMS=$(pwd) # you might want to set this env var in your .bashrc
$ make -f Makefile.TEOBResumS # you can also open the Makefile and set some options
$ ./TEOBResumS.x GW170817.par # this run should take ~ 2 s , runtime from initial frequencies <~ 20Hz is dominated by output of large data file
$ python ../Python/PlotWave.py -i GW170817/waveform_interp.txt -m "ai" -l "no" # show amplitude, real, imag part and do not show legend
```

The parfile can be found [here]({{site.url}}/assets/parfiles/GW170817.par).
That gives you the waveform sampled at 4096 Hz (Note the sampling is the reason you see so many "wiggles"):

![GW170817-TEOBResumS]({{site.url}}/assets/events/GW170817/GW170817_waveform_interp.png){:class="img-responsive"}

## References

 * Nagar et al (2018) [Time-domain effective-one-body gravitational waveforms for coalescing compact binaries with nonprecessing spins, tides and self-spin effects](https://inspirehep.net/record/1676430)
 * Akcay, Bernuzzi, Messina, Nagar, Ortiz, Rettegno (2018) [Effective-one-body multipolar waveform for tidally interacting binary neutron stars up to merger](http://inspirehep.net/record/1707624)
 * Nagar, Messina, Rettegno, Bini, Damour, Geralico, Akcay, Bernuzzi (2018) [Nonlinear-in-spin effects in effective-one-body waveform models of spin-aligned, inspiralling, neutron star binaries](https://inspirehep.net/record/1710050) 

