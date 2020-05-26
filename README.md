# Hands-on binfit tutorial notebook

Tutorial for the [binfit](https://stash.desy.de/users/sutclw/repos/binfit)
package developed for template fits in Belle II analyses.

## Background information on `binfit` and relation to `TemplateFitter`

`binfit` is a python package for performing template fits in pure python
developed and maintained by [William
Sutcliffe](mailto:william.sutcliffe08@gmail.com).

Its code is based in large parts on [Maximillian
Welsch](mailto:mwelsch@uni-bonn.de)'s `TemplateFitter` package, which is also
openly [available on github](https://github.com/welschma/TemplateFitter).

Another fork of the `TemplateFitter` package is being actively developed by
[Felix Metzner](mailto:felix.metzner@kit.edu), also [on
github](https://github.com/FelixMetzner/TemplateFitter). As far as I understand
he extends it generalizes the template fitter, e.g. with support for arbitrary
dimensions, adaptive binning.

## Features

The distinguishing feature of `binfit` from the other `TemplateFitter` packages,
is that it gets rid of for-loops over the decay-channels in the fit by
using matrix multiplications for all operations.


## Other references / tutorials

An already existing example notebook can be found in the
[binfit/examples/](https://stash.desy.de/users/sutclw/repos/binfit/browse/binfit/examples)
directory of the packages. It requires you to clone binfit (see *Installation*
section below). I will take inspiration from that.

There is a `docs/` directory which is meant to contain sphinx package
documentation (what basf2 uses) in RestructuredText (rst format), but the
installation instructions there are outdated. Maybe that will change. Feel free
to contribute if you want.

Max had already given a nice tutorial for his package at the October 2019 B2GM.
In his talk he gave a very nice overview on the theory of template fitting, so I
recommend you to look at his
[slides](https://indico.belle2.org/event/1158/contributions/4726/attachments/2809/4241/b2gm_templatefitter.pdf).
If you want to try out Max' `TemplateFitter`, e.g. to compare it to `binfit`,
there's already good
[tutorials](https://github.com/welschma/TemplateFitter/blob/master/examples/basic_example.ipynb)
in his packages `examples` folder. Also, his package has a nice sphinx
[online-documentation on
readthedocs](https://templatefitter.readthedocs.io/en/latest/index.html).

## Tutorial author

[Michael Eliachevitch](mailto:meliache@uni-bonn.de "email")
