# GRCon2020 workshop: Decoding interplanetary spacecraft

This repository contains material for the workshop "Decoding interplanetary
spacecraft" by Daniel Estévez at GRCon2020 on 14 September 2020. The material
supplied here will be useful to attendants to the workshop who want to follow
along using their own computers, and for reference after the workshop.

The work is centred around building GNU Radio flowgraphs to analyze and
demodulate deep-space probes IQ recordings.

By now, this repository only holds some of the material, and the IQ recordings,
which are recommended to be downloaded before the workshop. When the workshop
date comes closer, more material will be added.

## Requirements

The flowgraphs created in the workshop need the following:

* [GNU Radio 3.8](https://www.gnuradio.org/)

* [gr-satellites](https://github.com/daniestevez/gr-satellites) (any version
  since v3.0.0 is fine)

* [gr-dslwp](https://github.com/daniestevez/gr-dslwp/tree/maint38), branch
  `maint38`

There is also a very brief part of the workshop that uses a Jupyter
notebook. This needs:

* [Jupyter](https://jupyter.org/)
* [NumPy](https://numpy.org/)
* [Matplotlib](https://matplotlib.org/)
* [construct](https://construct.readthedocs.io/)

If someone faces problems installing any of the above, I'm welcome to help in
the issues of this repository. Also, note the following:

gr-satellites will only be used for the AGC, so instead of
installing gr-satellites, it is also possible to download and generate the
[AGC hierarchical
flowgraph](https://github.com/daniestevez/gr-satellites/blob/master/python/hier/rms_agc.grc)

gr-dslwp will only be used for Turbo decoding in the last part of the
workshop. Most of the workshop can be followed without gr-dslwp.

It is possible to test that GNU Radio and the OOT modules are working correctly
by using the `handson_09_turbo_decode.grc` flowgraph. Jupyter and related python
packages can be tested with the `Frames.ipynb` notebook.

## Recordings

The IQ recordings that will be used in this workshop can be downloaded
[here](http://eala.destevez.net/~daniel/grcon2020-workshop/). They should be
placed in the `recordings/` folder inside this repository. This files are almost
1GB large, so attendants are recommended to download these before the workshop.

## Licensing

This material is released under the [CC BY 4.0
license](https://creativecommons.org/licenses/by/4.0/)
