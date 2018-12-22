---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

Welcome! Here you find gravitational waveforms (GWs) compatible with
LIGO-Virgo events and computed the state-of-art effective-one-body
model [`TEOBResumS`]({{site.url}}/about/). 

`TEOBResumS` solves the general relativistic two-body problem and
generates dynamics and waveforms of colliding black holes and neutron
star binaries. It can be used to analyze the GW data with match
filtering techniques and to extract the source parameters as well as
to predict new waveforms. 
It describes motion and radiation of the coalescence process, from the
low-frequency quasi-circular inspiral regime all the way to merger
(and ringdown, for black hole binaries). 

![Fig:GW140915-TEOBResumS-and-signal](TODO){:class="img-responsive"}

## Waveforms

`TEOBResumS` parfiles and waveforms are given in the table below. A summary of the GW transients of compact binary mergers observed by LIGO and Virgo during the first (O1) and second (O2) observing runs is given in the [GWTC-1](https://inspirehep.net/record/1706018) paper.

> > **Disclaim**: The waveforms below do not correspond to any "best" match of the data. They are computed with source parameters values within the 90% confidence region for illustration purposes. Some uncertain parameters are even chosen arbitrarily. 


| Name | Masses [Mo] | Spins [Sz/M^2] | Distance [Mpc] | Lambda's | Data |
|---|---|---|---|
{% for e in site.events %}| {{ e.name }} | {{e.masses}} | {{e.spins}} | {{e.distance}} | {{e.lambdas}} | [![Download]({{site.url}}/assets/images/download-from-cloud.png){:height="20px" class="img-responsive"}]({{site.url}}/assets/events/{{ e.name }}/) |
{% endfor %}

Table: Masses are given in solar masses [Mo], spin values are dimensionless. All the waveforms are sampled at 4096 Hz; time units are given in seconds. Parameters Lambda is the quadrupolar tidal polarizability of each star.

