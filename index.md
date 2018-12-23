---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

Welcome! Here you find gravitational waveforms (GWs) compatible with
LIGO-Virgo events and computed the state-of-art effective-one-body
model [`TEOBResumS`]({{site.baseurl}}/about/). 

`TEOBResumS` solves the general relativistic two-body problem and
generates dynamics and waveforms of colliding black holes and neutron
star binaries. It can be used to analyze the GW data with match
filtering techniques and to extract the source parameters as well as
to predict new waveforms. 
It describes motion and radiation of the coalescence process, from the
low-frequency quasi-circular inspiral regime all the way to merger
(and ringdown, for black hole binaries). 

[![Fig:GW140915-TEOBResumS-and-signal]({{site.baseurl}}/assets/images/Fig16-grqc-1806.01772.png){:class="img-responsive"}](https://arxiv.org/abs/1806.01772)

## Waveforms

`TEOBResumS` parfiles and waveforms are given in the table below. A summary of the GW transients of compact binary mergers observed by LIGO and Virgo during the first (O1) and second (O2) observing runs is given in the [GWTC-1](https://inspirehep.net/record/1706018) paper.

> **Disclaim**: The waveforms below do not correspond to any "best match" of the data. They are computed with source parameters values within the 90% confidence region for illustration purposes. Some uncertain parameters are even chosen arbitrarily. 


| Name | Masses | Spins | Distance | f0 | Lambda's | Data |
|---|---|---|---|
{% for e in site.events %}| {{ e.name }} | {{e.masses}} | {{e.spins}} | {{e.distance}} | {{e.f0}} | {{e.lambdas}} | [![Download]({{site.baseurl}}/assets/images/download-from-cloud.png){:height="20px" class="img-responsive"}]({{site.baseurl}}/assets/events/{{ e.name }}/{{ e.name }}.tgz) |
{% endfor %}

**Table**: Masses are given in Solar masses; spin values are in geometric units and mass-rescaled (Sz/M^2); distance is in Mpc; the initial GW frequency is in Hz. Lambda is the quadrupolar tidal polarizability of each star. All the waveforms are sampled at 4096 Hz; time units are given in seconds. 


> **Note**: All this is experimental and under construction! Help us sending feedback on the `TEOBResumS` code/repo, the website and by [computing/adding events]({{site.baseurl}}/howto/) yourself!
