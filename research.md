---
layout: single
permalink: /research/
title: "Research projects"
author_profile: true
classes: wide
---

### Primordial Non-Gaussianity response of bias-zero tracers

Constraining primordial non-Gaussianities (PNG) is one of the main goals of the new generation of large-scale galaxy surveys, such as DESI or Euclid.
Local PNG leave a characteristic imprint on the clustering of galaxies on very large scales: a scale-dependent bias that grows as $$k^{-2}$$.
It had been proposed that *unclustered* tracers, i.e. samples with linear bias $$b_1=0$$, could be optimal for PNG studies, since their
clustering signal would then be dominated entirely by the PNG term, free from cosmic variance. These tracers could in principle be found by
selecting galaxies in bins of their local density.

<figure>
    <img src="{{ '/assets/images/research/power_spectra.png' | relative_url }}" style="width:500px; height:auto;" alt="Theoretical power spectra for tracers with different bias and PNG">
    <figcaption>Theoretical auto-power spectra for matter, a biased tracer with and without PNG, an unclustered tracer that follows the universality
    relation (green), and an unclustered tracer with no PNG response (black). If bias-zero tracers kept their PNG response, they would provide a very clean
    PNG signal; if not, they carry no information at all.</figcaption>
</figure>

During my Master's Thesis at CIEMAT, and later extended into a paper, we tested this hypothesis using the state-of-the-art PNG-UNITsim suite
of $$N$$-body simulations, with local $$f_{\rm NL}=100$$ and $$f_{\rm NL}=-20$$. We considered several parent tracer catalogues: all halos together,
halos in mass bins, and Halo Occupation Distribution (HOD) models reproducing DESI's Luminous Red Galaxies (LRG) and quasars (QSO). We then classified
these tracers by their local density, $$\delta_{t,R}$$, and measured both their linear bias ($$b_1$$) and their PNG response ($$b_\phi$$).

We found that the PNG response of these samples is compatible with $$b_\phi=0$$ for all bias-zero tracers considered. For high-mass halos, LRG and QSO
we recover a trend close to the universality relation, $$b_\phi = 2\delta_{\rm crit}(b_1-1)$$, for $$b_1>1$$, but the $$b_\phi(b_1)$$ curve flattens
to zero for $$|b_1|<1$$. The complex density-based selection makes the clustering of these samples deviate strongly from the usual assumptions
(universality and Poisson shot noise), which hinders their capability to constrain PNG. In short: **unclustered tracers remain unclustered**.

<figure>
    <img src="{{ '/assets/images/research/bphi_vs_b1.png' | relative_url }}" style="width:600px; height:auto;" alt="PNG response as a function of linear bias">
    <figcaption>PNG response (\(b_\phi\)) as a function of the measured linear bias (\(b_1\)) for tracers binned in their local overdensity.
    <b>Top:</b> all halos of the PNG-UNITsim (purple band) and halos in mass bins (markers). <b>Bottom:</b> LRG and QSO from the PNG-UNITsim-XL.
    The dot-dashed line shows the universality relation. Around \(b_1=0\), the PNG response is well below universality and compatible with zero.</figcaption>
</figure>

Publications:
<ul>
    <li>Merino C, Avila S, Adame AG, Anguren A, Gonzalez-Perez V, Meneses-Rizo J (2026). Unclustered tracers remain unclustered: the lack of primordial
    non-Gaussianity response of bias-zero tracers. <em>Astronomy &amp; Astrophysics</em>, 707, L15.
    <a href="https://doi.org/10.1051/0004-6361/202558825">doi.org/10.1051/0004-6361/202558825</a>
    (<a href="https://arxiv.org/abs/2602.04698">arXiv:2602.04698</a>)</li>
</ul>

Datasets:
<ul>
    <li>PNG-UNITsim and UNIT simulations, publicly available at <a href="http://www.unitsims.org/">unitsims.org</a> and
    <a href="https://opendata.pic.es/unitsims">PIC Open Data</a>.</li>
</ul>
