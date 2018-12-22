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

For a quick start with the binary neutron star event [GW170817](https://www.gw-openscience.org/events/GW170817/), you simply need to 

 1. Clone the code
 2. Compile the code (You need: the [`GCC`](https://gcc.gnu.org/) compiler and standard libs, including [`GSL`](https://www.gnu.org/software/gsl/doc/html/index.html), and [`Make`](https://www.gnu.org/software/make/))
 3. Run it with [this parfiles]({{site.baseurl}}/assets/events/GW170817/GW170817.par)
 4. Plot the result using e.g. [this]({{site.baseurl}}/assets/python/PlotWave.py) `python` script (that you can find also in the repo)

Get your waveform in four commands:

```
$ git clone git@bitbucket.org:eob_ihes/teobresums.git
$ cd /PATH/TO/teobresums/C
$ export TEOBRESUMS=$(pwd) # you might want to set this env var in your .bashrc
$ make -f Makefile.TEOBResumS # you can also open the Makefile and set some options
$ ./TEOBResumS.x GW170817.par # this run should take ~ 2 s , runtime from initial frequencies <~ 20Hz is dominated by output of large data file
$ python ../Python/PlotWave.py -i GW170817/waveform_interp.txt -m "ai" --no-legend # show amplitude, imag part and do not show legend
```

That gives you the GW170817 waveform sampled at 4096 Hz:

![Fig:GW170817-TEOBResumS]({{site.baseurl}}/assets/events/GW170817/GW170817_waveform_interp.png){:class="img-responsive"}

## References

 * Nagar et al (2018) [Time-domain effective-one-body gravitational waveforms for coalescing compact binaries with nonprecessing spins, tides and self-spin effects](https://inspirehep.net/record/1676430)
 * Akcay, Bernuzzi, Messina, Nagar, Ortiz, Rettegno (2018) [Effective-one-body multipolar waveform for tidally interacting binary neutron stars up to merger](http://inspirehep.net/record/1707624)
 * Nagar, Messina, Rettegno, Bini, Damour, Geralico, Akcay, Bernuzzi (2018) [Nonlinear-in-spin effects in effective-one-body waveform models of spin-aligned, inspiralling, neutron star binaries](https://inspirehep.net/record/1710050) 

