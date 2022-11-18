# Predicting Particle Size Distribution Using RNN

## Background

Here, `particle` means solid or liquid stuff that can suspend in the air, sizes from nanometers to micrometers, not atoms, protons, etc.

Ambient Particle Number Size Distribution (PNSD) is a key factor influencing health, air quality, and climate, but its data availability is still limited. Recurrent Neural Network (RNN) models are built to depict the aerosol number size distribution from trace gas concentrations, meteorological parameters, and total particle number concentration.

### Basic Concepts

Information for those outside the field of atmospheric science, PNSD, denoted as `dN/dlogDp` by convention. For ease of understanding, but not going into rigorous details, this crazy symbol is broken down as follows:

- `dlogDp`: differential (`d`) of particle diameter (`Dp`) take the logarithmic (`log`)
- `dN`:  differential (`d`) of total particle number concentration less than `Dp`

So `dN/dlogDp` is in the unit of the number of particles per unit volume ($cm^{-3}$). Usually, people use nanometer ($nm$) or meter ($m$) as the unit of `Dp`.

For example, if there are 100 particles per $cm^{3}$ ($dN=100$) between 10 and 100 $nm$, then the average `dN/dlogDp` of this size range is $100$, because the size spans an order of magnitude ($dlogDp=log100-log10=1$).

### Data Acquisition

All training data are open data from [SMEAR](https://www.atm.helsinki.fi/SMEAR/) stations are available [online](https://smear.avaa.csc.fi/).

#### Inputs
- Meterological Parameters
    - WS: Wind Speed
    - WD: Wind Direction
    - T: Temperature
    - RH: Raletive Humidity
    - P: Pressure
- Trace Gases
    - NO<sub>x</sub> = NO + NO<sub>2</sub>: Nitric Oxide + Nitrogen Dioxide
    - SO<sub>2</sub>: Sulfur Dioxide
    - CO: Carbon Monoxide
    - O<sub>3</sub>: Ozone
- N<sub>tot</sub>: Total Particle Number Concentration

#### Output
- PNSD

### Data Wrangling
- [Inspect raw data](https://colab.research.google.com/drive/1jFsD-2S-5tRz7fEHLoEE5PAtyWl3dTHY) by plotting all time-series figures.
- [Download raw data](https://colab.research.google.com/drive/1YE9owmBAdXRGRc3GGgjkzEa_bhPw73xO) using API.