# Machine Learning Challenge

## Description
Over a period of nine years in deep space, the NASA Kepler space telescope has been out on a planet-hunting mission to discover hidden planets outside of our solar system.
To help process this data, machine learning models were created capable of classifying candidate exoplanets from the raw dataset.
The classification consisted of:

* Preprocessing the raw data
* Tuning the models
* Comparing two or more models

![Figure1](Images/exoplanets.jpg)

## Data Preparation
* The raw data contained 41 features described in the Appendix A.
* The features related to measurement errors were dircarded, as well as the Planet number. The data for analysis cotains 19 featues after cleaning.

## Appendix A - Raw Data Description
Descriptions From: https://exoplanetarchive.ipac.caltech.edu/docs/API_kepcandidate_columns.html#id_col

Koi
Kepler Objecs of Interest: A KOI is a target identified by the Kepler Project that displays at least one transit-like sequence within Kepler time-series photometry that appears to be of astrophysical origin and initially consistent with a planetary transit hypothesis.

koi_disposition
Table Label: Exoplanet Archive Disposition
Description:  The category of this KOI from the Exoplanet Archive. Current values are CANDIDATE, FALSE POSITIVE, NOT DISPOSITIONED or CONFIRMED. All KOIs marked as CONFIRMED are also listed in the Exoplanet Archive Confirmed Planet table. Designations of CANDIDATE, FALSE POSITIVE, and NOT DISPOSITIONED are taken from the Disposition Using Kepler Data.

koi_fpflag_nt
Table Label: Not Transit-Like Flag
Description: A KOI whose light curve is not consistent with that of a transiting planet. This includes, but is not limited to, instrumental artifacts, non-eclipsing variable stars, and spurious (very low SNR) detections.

koi_fpflag_ss
Table Label: Stellar Eclipse Flag
Description: A KOI that is observed to have a significant secondary event, transit shape, or out-of-eclipse variability, which indicates that the transit-like event is most likely caused by an eclipsing binary. However, self-luminous, hot Jupiters with a visible secondary eclipse will also have this flag set, but with a disposition of PC.

koi_fpflag_co
Table Label: Centroid Offset Flag
Description: The source of the signal is from a nearby star, as inferred by measuring the centroid location of the image both in and out of transit, or by the strength of the transit signal in the target's outer (halo) pixels as compared to the transit signal from the pixels in the optimal (or core) aperture.

koi_fpflag_ec
Table Label: Ephemeris Match Indicates Contamination Flag
Description: The KOI shares the same period and epoch as another object and is judged to be the result of flux contamination in the aperture or electronic crosstalk.

koi_period
Table Label: Orbital Period (days)
Description: The interval between consecutive planetary transits.

koi_period_err1
Table Label: Uncertainty
Description: positive +

koi_period_err2
Table Label: Uncertainty
Description: negative -

koi_time0bk
Table Label:  Transit Epoch (BJD - 2,454,833.0)
Description: The time corresponding to the center of the first detected transit in Barycentric Julian Day (BJD) minus a constant offset of 2,454,833.0 days. The offset corresponds to 12:00 on Jan 1, 2009 UTC.

koi_time0bk_err1
Table Label: Uncertainty
Description: positive +

koi_time0bk_err2
Table Label: Uncertainty
Description: negative –

koi_impact
Table Label: Impact Parameter
Description: The sky-projected distance between the center of the stellar disc and the center of the planet disc at conjunction, normalized by the stellar radius.
koi_impact_err1
Table Label: Uncertainty
Description: positive +

koi_impact_err2
Table Label: Uncertainty
Description: negative –

koi_duration
Table Label: Transit Duration (hours)
Description: The duration of the observed transits. Duration is measured from first contact between the planet and star until last contact. Contact times are typically computed from a best-fit model produced by a Mandel-Agol (2002) model fit to a multi-quarter Kepler light curve, assuming a linear orbital ephemeris.

koi_duration_err1
Table Label: Uncertainty
Description: positive +

koi_duration_err2
Table Label: Uncertainty
Description: negative –

koi_depth
Table Label: Transit Depth (parts per million)
Description: The fraction of stellar flux lost at the minimum of the planetary transit. Transit depths are typically computed from a best-fit model produced by a Mandel-Agol (2002) model fit to a multi-quarter Kepler light curve, assuming a linear orbital ephemeris

koi_depth_err1
Table Label: Uncertainty
Description: positive +

koi_depth_err2
Table Label: Uncertainty
Description: negative –

koi_prad
Table Label: Planetary Radius (Earth radii)
Description: The radius of the planet. Planetary radius is the product of the planet star radius ratio and the stellar radius.

koi_prad_err1
Table Label: Uncertainty
Description: positive +

koi_prad_err2
Table Label: Uncertainty
Description: negative –

koi_teq
Table Label: Equilibrium Temperature (Kelvin)
Description: Approximation for the temperature of the planet. The calculation of equilibrium temperature assumes a) thermodynamic equilibrium between the incident stellar flux and the radiated heat from the planet, b) a Bond albedo (the fraction of total power incident upon the planet scattered back into space) of 0.3, c) the planet and star are blackbodies, and d) the heat is evenly distributed between the day and night sides of the planet.

koi_insol
Table Label: Insolation Flux [Earth flux]
Description: Insolation flux is another way to give the equilibrium temperature. It depends on the stellar parameters (specifically the stellar radius and temperature), and on the semi-major axis of the planet. It's given in units relative to those measured for the Earth from the Sun.

koi_insol_err1
Table Label: Uncertainty
Description: positive +

koi_insol_err2
Table Label: Uncertainty
Description: negative –

koi_model_snr
Table Label: Transit Signal-to-Noise
Description: Transit depth normalized by the mean uncertainty in the flux during the transits.

koi_tce_plnt_num
Table Label: TCE Planet Number
Description: TCE Planet Number federated to the KOI.

koi_steff
Table Label: Stellar Effective Temperature (Kelvin)
Description: The photospheric temperature of the star.

koi_steff_err1
Table Label: Uncertainty
Description: positive +

koi_steff_err2
Table Label: Uncertainty
Description: negative –

koi_slogg
Table Label: Stellar Surface Gravity (log10(cm s-2)
Description: The base-10 logarithm of the acceleration due to gravity at the surface of the star.

koi_slogg_err1
Table Label: Uncertainty
Description: positive +

koi_slogg_err2
Table Label: Uncertainty
Description: negative –

koi_srad
Table Label: Stellar Radius (solar radii)
Description: The photospheric radius of the star

koi_srad_err1
Table Label: Uncertainty
Description: positive +

koi_srad_err2
Table Label: Uncertainty
Description: negative -

ra
Table Label:  RA (deg)
Description: KIC Right Ascension – KIC: Kepler Input catalog

dec
Table Label:  Dec (deg)
Description:  KIC Declination


koi_kepmag
Table Label:  Kepler-band (mag)
Description: Kepler-band (mag)


