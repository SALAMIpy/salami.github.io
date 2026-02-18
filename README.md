# SALAMI Dataset

An Artificial Intelligence / Machine Learning (AI/ML)-ready dataset for geomagnetic storms, combining NASA OMNI data, NASA Solar Dynamics Observatory (SDO) mission data, Geostationary Operational Environmental Satellite (GOES) Solar Ultraviolet Imager (SUVI) data, and Global Osccilations Network Group (GONG) data.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)]()

## Data Overview

Both operational and scientific space weather data have been collected by multiple missions since the late 20th century. Preeminent among these have been NASA SDO, NOAA DSCOVR, NASA ACE, and more recently, GOES/SUVI, and GONG. Together, these platforms have provided the heliophysics community with extensive measurements of the causes and effects of solar and geomagentic activity.
1. SDO's Atmospheric Imaging Assembly (AIA; [Lemen, et al. 2012](https://link.springer.com/content/pdf/10.1007/s11207-011-9776-8.pdf)) provides 4096x4096 images of the full solar disk in 9 bandpasses, capturing processes occurring throughout the solar atmosphere at 12 second resolution.
2. NOAA's Deep Space Climate Observatory (DSCOVR; [Burt and Smith, 2012](https://ieeexplore.ieee.org/abstract/document/6187025/)) PlasMag instrument suite provides measuremetns of solar wind speed, density, temperature, and magnetic field at the Earth-Sun L1 Lagrange point at <1 s temporal resolution.
3. NASA's Advanced Composition Explorer (ACE; [Zwicki, et al. 1998](https://link.springer.com/article/10.1023/A:1005044300738)) uses its Real-Time Solar Wind system to monitor the solar wind at the Earth-Sun Lagrange L1 point at <1 min temporal resolution.
4. NOAA's GOES-R SUVI instrument ([Darnell, et al. 2022](https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2022SW003044)) provides 1280x1280 images of the full solar disk in 6 Extreme Ultraviolet Bandpasses every four minutes.
5. GONG's global network of six Michelson Interferometers ([Harvey, et al. 1996](https://www.science.org/doi/abs/10.1126/science.272.5266.1284)) uses detections of resonating acoustic waves in the solar atmosphere to produce full disk images of pixel velocity, intensity, and magnetic-flux at 1 minute temporal resolution.

The solar wind measurements in particular have been combined with longstanding measurements of solar and and geomagnetic activity, and are provided in the [NASA OMNI Database](https://omniweb.gsfc.nasa.gov/). To supplement the solar imagery, researcher have also taken historical measurements of the solar EUV spectrum and formed a the Flare Irradiance Spectrum [Chamberlin, et al. 2020](https://agupubs.onlinelibrary.wiley.com/doi/abs/10.1029/2020sw002588), a model of the entire solar EUV spectrum between 0.01 and 190 nm at 0.1 nm resolution.

## The SALAMI Dataset

The SALAMI dataset takes _all_ of the above data and arranges into an AI/ML-ready format. Heavily inspired by the success of this approach as applied to SDO mission data in particular [Galvez, et al. 2019]https://iopscience.iop.org/article/10.3847/1538-4365/ab1005), the SALAMI database consists of multi-channel space weather observations arranged into an AI/ML ready format. Notable aspects of SALAMI are as follows:
1. SALAMI data is focused on geomagnetic storms. All data are aggregated into samples, with each sample covering a historical storm period.
2. Storms are labeled by intensity, and associated with metadata related to storm duration and timing of storm phases.
3. SALAMI provides utilities for cross-referencing storms with solar flares catalogues in [NASA CCMC's DONKI Database](https://www.google.com/url?sa=t&source=web&rct=j&opi=89978449&url=https://kauai.ccmc.gsfc.nasa.gov/DONKI/&ved=2ahUKEwi95dmNxOOSAxXByckDHaI2EKkQFnoECBwQAQ&usg=AOvVaw0hRCtF7HddEn0WyOcEsjbK). Combined with tools for downloading SDO/AIA Level 1 data, users can develop ML workflows to specifically investigate precursors to geomagnetic events.

## Intended Users

The SALAMI database is intended primarily for those interested in space weather forecasting, as well as researchers using AI/ML to investigate precursors to various geomagnetic events. Since much of the original data in the SALAMI dataset require a non-trivial amount of preprocessing (i.e. gappy solar wind time series) that requires domain-specific knowledge and detailed understanding of statistics, such preprocessing has been taken care of to minimize hurdles for researchers who wish to use data from multiple missions for space weather prediction.

The Google Colab link above contains a Jupyter Notebook that serves as an introduction for working with the dataset and exploring various functionalities.
