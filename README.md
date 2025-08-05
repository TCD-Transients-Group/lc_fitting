# Light-curve Fitting

Repository with tutorials for light-curve fitting of type Ia supernovae (SNe Ia) and other transients.
___

## Why do we need a light-curve fitter?

There are various reasons why you would need to fit light curves (LCs): get a continuous function to study the LC or colour-curve evolution in some given bands, to compare these with other transients, to obtain LC parameters to characterise the population of some transients, etc.

## Type of fitters

Independently of the reason for fitting light curves, the choice of LC fitter will depend on the transient. Normally, the aim is to obtain continuous **rest-frame** light curves, particularly for extragalactic transients like SNe. People also refer to the conversion of observer-frame to rest-frame photometry as *K*-corrections (e.g. [Oke & Sandage 1968](https://ui.adsabs.harvard.edu/abs/1968ApJ...154...21O/abstract), [Kim et al. 1996](https://ui.adsabs.harvard.edu/abs/1996PASP..108..190K/abstract), [Hsiao et al. 2007](https://ui.adsabs.harvard.edu/abs/2007ApJ...663.1187H/abstract)). This generally requires knowledge of the spectral energy distribution (SED) of the object in question. For this, SED templates can be used, although, ideally, these need to be built from a large dataset. Otherwise, data-driven approaches, such as Gaussian Process regression (GP; [Rasmussen & Williams 2006](https://ui.adsabs.harvard.edu/abs/2006gpml.book.....R/abstract)), can be used. However, the latter tends to be less precise. In summary, you have template- and data-driven fitters.

___

## LC Fitters

In this repository, three LC fitters will be presented: SALT2, PISCOLA and SNooPy. SALT2 and SNooPy are specific for fitting (mainly normal) SNe Ia, while PISCOLA is a more general fitter, based on GP, although initially built for fitting SNe Ia as well.

### SALT2

The Spectral Adaptive Light-curve Template (SALT) SNe Ia fitter was introduced in [Guy et al. (2005)](https://ui.adsabs.harvard.edu/abs/2005A%26A...443..781G/abstract) and then updated in [Guy et al. (2007)](https://ui.adsabs.harvard.edu/abs/2007A%26A...466...11G/abstract)(SALT2). The latter has been used in several cosmological analyses with SNe Ia. Since then, there has been a few different versions, but we will use SALT2, which is still more commonly used today.

#### SNCosmo

[SNCosmo](https://github.com/sncosmo/sncosmo) is a Python library for SN cosmology analysis. It includes different SN models, such as SALT2. We will use this to fit with SALT2. However, note that it has many other functionalities.

### PISCOLA

PISCOLA was presented in [Müller-Bravo et al. (2022)](https://ui.adsabs.harvard.edu/abs/2022MNRAS.512.3266M/abstract) and has greatly changed since its initial version. It is purely based on GP (i.e. it does not rely on templates) and can thus be used for any transient.

### SNooPy

The SuperNovae in Object Oriented Python (SNooPy) SNe Ia fitter was presented in [Burns et al. (2011)](https://ui.adsabs.harvard.edu/abs/2011AJ....141...19B/abstract) and then updated in [Burns et al. (2014)](https://ui.adsabs.harvard.edu/abs/2014ApJ...789...32B/abstract).

___

## Python environment

It is highly recommended to use environments and install pip in them as well:

```code
conda create -n <env_name> pip
```

All the requirements are the in the *requirements.txt* file, which can be easily installed:

```code
pip install -r requirements.txt
```

Note that SALT2 (SNCosmo) needs the *iminuit* package.
