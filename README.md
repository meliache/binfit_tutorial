# Hands-on binfit tutorial notebook

Tutorial for the [binfit](https://stash.desy.de/users/sutclw/repos/binfit)
package developed for template fits in Belle II analyses.

As of now this is simply an annoted version of the notebook that comes with
binfit in the `examples` directory. To get started with the tutorial, just open the
notebook [or click here](binfit_tutorial.ipynb).

## Background information on `binfit` and relation to `TemplateFitter`

`binfit` is a python package for performing template fits in pure python
developed and maintained by [William
Sutcliffe](mailto:william.sutcliffe08@gmail.com "email").

Its code is based in large parts on [Maximillian
Welsch](mailto:mwelsch@uni-bonn.de "email")'s `TemplateFitter` package, which is also
openly [available on github](https://github.com/welschma/TemplateFitter).

Another fork of the `TemplateFitter` package is being actively developed by
[Felix Metzner](mailto:felix.metzner@kit.edu "email"), also [on
github](https://github.com/FelixMetzner/TemplateFitter). As far as I understand
he extends it generalizes the template fitter, e.g. with support for arbitrary
dimensions, adaptive binning.

## Implementation / Features

The common features of the `binfit` an `TemplateFitter` / packages are (adapted from this
[`TemplateFitter` talk](https://indico.belle2.org/event/1158/contributions/4726/attachments/2809/4241/b2gm_templatefitter.pdf)):

- no reliance on ROOT: evaluation of the (log-)likelihood function relies on numpy operations
- supports minimization with both
  [scipy.optimize](https://docs.scipy.org/doc/scipy/reference/optimize.html)
  (LLSQ method) or [iminuit](https://iminuit.readthedocs.io/en/latest/)
  (standalone Minuit implementation in python).
- template likelihood fits (simultaneous in different channels)
- fix, create bounds or profile parameters
- different Toy MC study methods available

**`binfit`-specific:**

The distinguishing feature of `binfit` from the other `TemplateFitter` packages,
is that it gets rid of for-loops over the decay-channels in the fit by using
numpy matrix operations only. These are more performant, because numpy performs
the loops in performant C in the background.



## Other references / tutorials

An already existing example notebook can be found in the
[binfit/examples/](https://stash.desy.de/users/sutclw/repos/binfit/browse/binfit/examples)
directory of the packages. It requires you to clone binfit (see *Installation*
section below). I will take inspiration from that.

If you want to understand the **theory of template fitting**, I recommend
Maximillian Welsch's
[talk](https://indico.belle2.org/event/1158/contributions/4726/attachments/2809/4241/b2gm_templatefitter.pdf).
at the October 2019 B2GM.
For uncertainty handling, I recommend Markus
Prim's talk at the physics performance meeting: [Template Fitting Including
Systematics](https://indico.belle2.org/event/2170/contributions/10467/attachments/5564/8602/FittingWithSystematics.pdf)
([youtube](https://www.youtube.com/watch?v=RyBAOdGo8zI)).

If you want to try out Max' `TemplateFitter`, e.g. to compare it to `binfit`,
TemplateFitter also has good jupyter notebook
[tutorials](https://github.com/welschma/TemplateFitter/blob/master/examples/basic_example.ipynb).

## Tutorial author

[Michael Eliachevitch](mailto:meliache@uni-bonn.de "email")
