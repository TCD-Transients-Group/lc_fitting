# Light-curve Fitting

Repository with tutorials for light-curve fitting of type Ia supernovae (SNe Ia) and other transients.
___

## Why do we need a light-curve fitter?

There are various reasons why you would need to fit light curves (LCs): get a continuous function to study the LC or colour-curve evolution in some given bands, to compare these with other transients, to obtain LC parameters to characterise the population of some transients, etc.

## Type of fitters

Independently of the reason for fitting light curves, the choice of LC fitter will depend on the transient. Normally, the aim is to obtain continuous **rest-frame** light curves, particularly for extragalactic transients like SNe. People also refer to the conversion of observer-frame to rest-frame photometry as *K*-corrections (e.g. [Oke & Sandage 1968](https://ui.adsabs.harvard.edu/abs/1968ApJ...154...21O/abstract), [Kim et al. 1996](https://ui.adsabs.harvard.edu/abs/1996PASP..108..190K/abstract), [Hsiao et al. 2007](https://ui.adsabs.harvard.edu/abs/2007ApJ...663.1187H/abstract)). This generally requires knowledge of the spectral energy distribution (SED) of the object in question. For this, SED templates can be used, although these need to be built ideally from a large dataset. Otherwise, data-driven approaches, such as Gaussian Process regression (GP; [Rasmussen & Williams 2006](https://ui.adsabs.harvard.edu/abs/2006gpml.book.....R/abstract)), can be used. However, the latter tends to be less precise. In summary, you have template- and data-driven fitters.

## LC Fitters

In this repository, three LC fitters will be presented: SALT2, PISCOLA and SNooPy. SALT2 and SNooPy are specific for fitting (normal) SNe Ia, while PISCOLA is a more general fitter, based on GP, although initially built for fitting SNe Ia as well.
