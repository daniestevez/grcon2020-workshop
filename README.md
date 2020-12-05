# GRCon20 workshop: Decoding interplanetary spacecraft

This repository contains material for the workshop "Decoding interplanetary
spacecraft" by Daniel Estévez at [GRCon20](https://www.gnuradio.org/grcon/grcon20/)
on 14 September 2020. The recording of the workshop session can be found
in this [Youtube video](https://www.youtube.com/watch?v=RDbs6l4rMhs).

The material
supplied here was provided to attendees of the workshop to follow
along using their own computers, and for reference after the workshop.

The workshop is centred around building GNU Radio flowgraphs to analyze and
demodulate deep-space probes IQ recordings.

This repository contains a number of GNU Radio companion `.grc` files called
`handson_*.grc` that show the progress at different steps during the hands-on
part of the workshop with GNU Radio companion.

It also contains the PDF slides for the workshop in the folder `slides/`.

## GNU Radio Virtual Machine

Users of the [UbuntuVM](https://wiki.gnuradio.org/index.php/UbuntuVM) virtual
machine that includes GNU Radio can install the required software for the
workshop by following [the instructions
here](https://github.com/daniestevez/grcon2020-workshop/issues/1). Note you also
need to download the IQ recordings as indicated below.

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
flowgraph](https://github.com/daniestevez/gr-satellites/blob/master/python/hier/rms_agc.grc).

gr-dslwp will only be used for Turbo decoding in the last part of the
workshop. Most of the workshop can be followed without gr-dslwp.

It is possible to test that GNU Radio and the OOT modules are working correctly
by using the `handson_09_turbo_decode.grc` flowgraph. Jupyter and related python
packages can be tested with the `Frames.ipynb` notebook.

## Recordings

The IQ recordings that will be used in this workshop can be downloaded
[here](http://eala.destevez.net/~daniel/grcon2020-workshop/). They should be
placed in the `recordings/` folder inside this repository. These files total to nearly
1GB, so attendees are recommended to download these before the workshop.

## GNU Radio Logging

If you have a freshly installed GNU Radio or are using a Virtual Machine with
GNU Radio, then the default logging configuration will produce many debug
messages with some of the flowgraphs. These messages can make
`gnuradio-companion` run very slowly. It is recommended that you edit (or
create) `~/.gnuradio/config.conf` and enter into this file:

```
[log]
log_level = info
```

to reduce the number of debug messages.

## Licensing

This material is released under the [CC BY 4.0
license](https://creativecommons.org/licenses/by/4.0/).

## More recordings

Here is a list of recordings similar used to those used in the workshop. It can
serve as a basis for people interested in studying these topics further.

* [Recordings of Tianwen-1](http://gs1.to.ee/public_to117/Obs/Viljo/dsn/tianwen/)
  made by Viljo Allik ES5PC with the 4.5m dish at Tartu University
  (Estonia).
  See [this](https://destevez.net/2020/07/tianwen-1-telemetry-modulation-and-coding/)
  and related blogposts.

* [Short recording of Tianwen-1](https://drive.google.com/file/d/1jcH1S0vUzzEplE5SU5VIxp2HClwHUDf8/view)
  made by Wei Mingchuan BG2BHC with the 5.4m dish at Harbin Institute of Technology (China).
  The format is `complex64` (i.e., `float32` IQ) at 3Msps.
  Source: [this tweet](https://twitter.com/bg2bhc/status/1290650921349914624)

* [Emirates Mars Mission (Hope)](http://eala.destevez.net/~daniel/20200719_232945_99998.raw),
  recorded by Paul Marsh M0EYT. The format is `int16` IQ at 99998sps. See the
  [blog post](https://destevez.net/2020/07/decoding-emirates-mars-mission-hope/)
  for more information.

