# particle-size-distribution-rnn

## Background

`Particle` means solid or liquid stuff that can suspend in the air, sizes from nanometers to micrometers, not atoms, protons, etc.

Ambient Particle Number Size Distribution (PNSD) is a key factor influencing health, air quality, and climate, but its data availability is still limited. Recurrent Neural Network (RNN) models are built to depict the aerosol number size distribution from trace gas concentrations, meteorological parameters, and total particle number concentration.

### Basic concepts

Information for those outside the field of atmospheric science, PNSD, denoted as `dN/dlogDp` by convention. For ease of understanding, but not going into rigorous details，this crazy symbol is broken down as follows:

- `dlogDp`: differential (`d`) of particle diameter (`Dp`) take the logarithmic (`log`)
- `dN`:  differential (`d`) of total particle number concentration less than `Dp`

So `dN/dlogDp` is in the unit of the number of particles per unit volume ($cm^{-3}$). Usually, people use nanometer ($nm$) or meter ($m$) as the unit of `Dp`.

For example, if there are 100 particles between 10 and 100 $nm$, then the average `dN/dlogDp` of this size range is $100$, because the size spans an order of magnitude ($log100 - log10 = 1$).

---
