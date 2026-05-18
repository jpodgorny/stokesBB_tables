Table of contents
=================

* [Version](#version)
* [Description of STOKESBB tables](#description-of-STOKESBB-tables)
* [References](#references)
* [Parameter definitions for STOKESBB tables](#parameter-definitions-for-STOKESBB-tables)


Version
=================

Version 2.0.

This version contains the blackbody partially ionized reflection tables and blackbody
neutral reflection tables with all initial updates included.


Description of STOKESBB tables
==============================

The STOKESBB tables (Podgorný et al. 2022, 2026, Podgorný & Dovčiak 2026)
provide spectra and polarisation properties of reprocessed emission in a plane-parallel
slab illuminated by an X-ray source emitting single-temperature blackbody
radiation. The incident photons may have arbitrary polarisation. The reprocessing 
is precomputed and stored in FITS files, which are calculated for three different 
states of incident polarisation. The tables include the dependence on the geometry
of scattering defined by the incident, emission and azimuthal angles, θ<sub>i</sub>, 
θ<sub>e</sub> and φ. The slab is assumed to be optically thick, with a constant density of 
n<sub>H</sub>=10<sup>15</sup>cm<sup>-3</sup>. The blackbody illumination is
characterised by a temperature parameter, kT, with sharp low- and high-energy cut-offs
at E<sub>l</sub> ≈ 0.08 keV and E<sub>c</sub> ≈ 250 keV, causing ionisation of the slab, 
which is defined by the ionisation parameter, ξ. The ionisation structure of the slab
was computed using the TITAN code (Dumont et al. 2003), while the spectral shape and
polarisation properties of the reprocessed emission were computed using the STOKES code
(Goosmann & Gaskell 2007, Marin 2018). In addition, a pure neutral version of the
blackbody tables is available (Podgorný & Dovčiak 2026).

Note: for power-law reflection variant of these tables, please visit this repository:
[stokes_tables](https://github.com/jpodgorny/stokes_tables).

The provided tables conform to OGIP standards and can be directly used in XSPEC
using the `atable` command. Six FITS tables are available
for the Stoke parameters i, q and u with 160 bins in 2 to 80 keV
(the reduced version of the partially ionized tables with 70 bins in 2 to 10 keV
is also available at [stokesBB_tables_reduced-v2.0.tar.gz](https://owncloud.asu.cas.cz/index.php/s/3XxmISx4emRrqzB)):

* [stokesBB_unpol-v2.0.fits](https://owncloud.asu.cas.cz/index.php/s/LMphVANeazREZPk)
→ for unpolarised illumination; the parameters of these tables include kT, ξ,
μ<sub>i</sub>, μ<sub>e</sub> and φ,

* [stokesBB_vrpol-v2.0.fits](https://owncloud.asu.cas.cz/index.php/s/HZ9RHPO1mUzA0R1)
→ for fully polarised illumination in the vertical direction; the parameters of
these tables include kT, ξ, μ<sub>i</sub>, μ<sub>e</sub> and φ,

* [stokesBB_45deg-v2.0.fits](https://owncloud.asu.cas.cz/index.php/s/cdJ8UWAMQ7awSJ9)
→ for fully polarised illumination with a polarisation angle of 45° from the
vertical direction, measured counterclockwise; the parameters of
these tables include kT, ξ, μ<sub>i</sub>, μ<sub>e</sub> and φ.

* [stokesBB_unpol-neutral-v2.0.fits](https://owncloud.asu.cas.cz/index.php/s/X8ibfEsz3CG0b9r)
→ neutral for unpolarised illumination; the parameters of these tables include Γ,
μ<sub>i</sub>, μ<sub>e</sub> and φ,

* [stokesBB_vrpol-neutral-v2.0.fits](https://owncloud.asu.cas.cz/index.php/s/26nvPhEzgWw1T0Z)
→ neutral for fully polarised illumination in the vertical direction; the parameters of
these tables include Γ, μ<sub>i</sub>, μ<sub>e</sub> and φ,

* [stokesBB_45deg-neutral-v2.0.fits](https://owncloud.asu.cas.cz/index.php/s/du8x7wYTqXgpuAh)
→ neutral for fully polarised illumination with a polarisation angle of 45° from the
vertical direction, measured counterclockwise; the parameters of
these tables include Γ, μ<sub>i</sub>, μ<sub>e</sub> and φ.

The blackbody reflection Stokes parameters are additionally multiplied
by a 10<sup>-20</sup> factor for storage convenience, unlike the tables with a power law.
Isotropic versions are yet to be added, and the XSPEC corresponding models that can be found
for power-law reflection tables are yet to be constructed.

For any issues regarding the use of the STOKESBB tables, please, contact J.
Podgorný at [jakub.podgorny@asu.cas.cz](mailto:jakub.podgorny@asu.cas.cz) 
or M. Dovčiak at [michal.dovciak@asu.cas.cz](mailto:michal.dovciak@asu.cas.cz).


References
==========

Podgorný J, Dovčiak M, Marin F, Goosmann RW & Różańska A (2022)  
_Spectral and polarization properties of reflected X-ray emission from black hole accretion discs_  
[MNRAS, 510, pp.4723-4735](https://doi.org/10.1093/mnras/stab3714) 
[[arXiv:2201.07494](https://arxiv.org/abs/2201.07494)]

Podgorný J, Dovčiak M, Goosmann RW, Marin F, Marra L, Matt G, Różańska A & Taverna R (2026, submitted)
_X-ray polarization of reflected thermal emission_
[[arXiv:2507.23687](https://arxiv.org/abs/2507.23687)]

Podgorný J & Dovčiak M (2026)
_KY codes and STOKES tables_
(in prep.)

Dumont AM, Collin S, Paletou F, Coupé S, Godet O & Pelat D (2003)  
_Escape probability methods versus ``exact" transfer for modelling the X-ray spectrum of Active Galactic Nuclei and X-ray binaries_  
[A&A, 407, p.13-30](https://doi.org/10.1051/0004-6361:20030890) 
[[arXiv:astro-ph/0306297](https://arxiv.org/abs/astro-ph/0306297)]

Goosmann RW & Gaskell CM (2007)  
_Modeling optical and UV polarization of AGNs. I. Imprints of individual scattering regions_  
[A&A, 465, pp.129-145](https://doi.org/10.1051/0004-6361:20053555)
[[arXiv:astro-ph/0507072](https://arxiv.org/abs/astro-ph/0507072)]

Marin F (2018)  
_Modeling optical and UV polarization of AGNs. V. Dilution by interstellar polarization and the host galaxy_  
[A&A, 615, id.A171](https://doi.org/10.1051/0004-6361/201833225) 
[[arXiv:1805.09098](https://arxiv.org/abs/1805.09098)]


Parameter definitions for STOKESBB tables
=========================================

`stokesBB_unpol-v2.0.fits`, `stokesBB_vrpol-v2.0.fits` and `stokesBB_45deg-v2.0.fits`
-------------------------------------------------------------------------

Tables for unpolarised illumination, fully vertically polarised illumination and 
for fully polarised illumination with a polarisation angle of 45° counterclockwise 
from the vertical direction and a blackbody source.

* **par1 ... kT** [ 0.2 <= kT <= 10.0 ]
  - blackbody temperature of the incident flux in keV
* **par2 ... Xi** [ 10. <= Xi <= 20 000. ]
  - ionisation parameter of the slab
* **par3 ... Mui** [ 0. <= Mui <= 1. ]
  - cosine of the incident angle (0.-disc, 1.-pole)
* **par4 ... Phi** [ 7.5 <= Phi <= 352.5 ]
  - azimuthal scattering angle in degrees (0.-forward, 180.-backward)
* **par5 ... Mue** [ 0.025 <= Mue <= 0.975 ]
  - cosine of the emission angle (0.-disc, 1.-pole)

`stokesBB_unpol-neutral-v2.0.fits`, `stokesBB_vrpol-neutral-v2.0.fits` and `stokesBB_45deg-neutral-v2.0.fits`
-------------------------------------------------------------------------

Tables for unpolarised illumination, fully vertically polarised illumination and
for fully polarised illumination with a polarisation angle of 45° counterclockwise
from the vertical direction, from a cold slab and a blackbody source.

* **par1 ... kT** [ 0.2 <= kT <= 10.0 ]
  - blackbody temperature of the incident flux in keV
* **par2 ... Mui** [ 0. <= Mui <= 1. ]
  - cosine of the incident angle (0.-disc, 1.-pole)
* **par3 ... Phi** [ 7.5 <= Phi <= 352.5 ]
  - azimuthal scattering angle in degrees (0.-forward, 180.-backward)
* **par4 ... Mue** [ 0.025 <= Mue <= 0.975 ]
  - cosine of the emission angle (0.-disc, 1.-pole)
