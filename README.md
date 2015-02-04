# claretld

Python interface for retrieving limb-darkening parameters from [Claret et al. 2013](http://cdsads.u-strasbg.fr/cgi-bin/nph-bib_query?2013A%26A...552A..16C&db_key=AST&nosetcookie=1) via [Vizier](http://vizier.u-strasbg.fr/viz-bin/VizieR-3?-source=J/A%2bA/552/A16/limb1-4). The first time you `import claretld` it will download the data table from Vizier and save a local binary copy (1.1 MB). Subsequent imports will load the local copy (from the same directory as the claretld.py file).

### Usage

```python
# Get quadratic limb-darkening parameters for a star with effective temperature
# 5800 K and log g = 4.0, in the K band:
>>> from claretld import quad, u2q
>>> print quad(5800, 4.0, 'K')
(0.13200000000000001, 0.183)

## Convert the two quadratic parameters into Kipping 2013's q1 and q2 terms
>>> print u2q(*quad(5800, 4.0, 'K'))
(0.099225000000000008, 0.20952380952380953)
```

### Requirements
* Python 2+ 
* Numpy

### Available filters

Kepler, CoRoT, Spitzer (IRAC), uvby (Strömgren), UBVRIJHK (Johnson-Cousins), Sloan, and 2MASS.

### Contact

[Brett Morris](http://staff.washington.edu/bmmorris/): bmmorris@uw.edu
