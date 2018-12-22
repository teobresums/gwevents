---
layout: page
title: AddYourEvent
permalink: /howto/
---

We did not add waveforms for all the events abserved so far.
Your are welcome to add your favourite GW `TEOBResumS` event to this website.
Be quick: there's a limited number of events!

Steps:

 1. Have a look at LIGO-Virgo papers and to [GW Open Science Center](https://www.gw-openscience.org/about/)
 2. Clone and get familar with the [`TEOBResumS`](https://bitbucket.org/eob_ihes/teobresums/src/master/) code (see also [here](/about/) for a quick start)
 3. Produce a waveform corresponding to your favourite event
 4. Push it to our GitHub [`gwevents`](https://github.com/teobresums/gwevents/) repo

and it will appear on this website.

## What and How to push

Here we give you some tips on what and how to push.
We assume you are familiar with basic Linux `bash` commands and [`git`](https://git-scm.com/) (see also a [quick tutorial](https://gitlab.com/bernuzzi/gitandgo)).
Fork our [`gwevents`](https://github.com/teobresums/gwevents/) repo, clone your fork and work there.
When ready, make a pull request: we will merge as soon as we have some time to work on it :)

To start, please, take a moment to study the repo structure. The website is created with [`jekyll`](https://jekyllrb.com/) but you do not need to learn that in detail; just follow this tutorial.

Lets say you have produce a `TEOBResumS` waveform corresponding to event `GWYYMMDD`.
Make a tarball with the data interpolated at 4096 Hz (output file `waveform_interp.txt`), the parfile and a plot of the data:

```
$ tar zcvf GWYYMMDD.tgz waveform_interp.txt GWYYMMDD.par GWYYMMDD_waveform_interp.png
$ ls -h GWYYMMDD.tgz # check how big is the tarball
```

and be sure the tarball is smaller than, say, 20M (but typical size should be 2M).

Then, create a folder with the event's name in the `gwevents` repo and copy there the data:

```
$ mkdir PATH/TO/YOUR/REPO/gwevents/assets/events/GWYYMMDD
$ cp GWYYMMDD.tgz PATH/TO/YOUR/REPO/gwevents/assets/events/GWYYMMDD/
$ cp GWYYMMDD.par PATH/TO/YOUR/REPO/gwevents/assets/events/GWYYMMDD/
$ cp GWYYMMDD_waveform_interp.png PATH/TO/YOUR/REPO/gwevents/assets/events/GWYYMMDD/
```
Now add the event properties in a `markdown` (text) file, by doing

```
$ cd PATH/TO/YOUR/REPO/gwevents/
$ cp _events/GW170817.md _events/GWYYMMDD.md
```

and editing `_events/GWYYMMDD.md` accordingly, it is really simple. These info will end up in the website table.

Before `git` adding/pushing, would be better to check locally that you did not break anything. Run the following command

```
$ bundle exec jekyll serve --config _config.yml,_config_local.yml
```

and open `http://127.0.0.1:4000` with your browser: you should see the website with your additions.
Note you need `jekyll` installed locally todo that; otherwise you will to check later from `GitHub` pages.

Finally, you are ready to add/push on branch `gh-pages`:

```
git push origin gh-pages
```

Done!



