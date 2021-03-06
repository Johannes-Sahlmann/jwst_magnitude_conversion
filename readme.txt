The JWST Magnitude Conversion Program

  The code and files in this directory allow one to make an approximate
transformation of other filter magnitudes to the expected JWST magnitudes.
The transformation depends on theoretical relations between the different
magnitudes as simulated from stellar atmosphere model spectra.

  There are five files that are essential, the program itself and four sets
of simulated magnitudes for different spectral grid sets:

jwst_magnitude_converter.py         the program
magslist_bosz_normal.new            simulated colours from the Bohlin et al. (2017) Altas9 models
                                    using the models with scaled solar abundances
magslist_blackbody.new              simulated blackbody colours
magslist_old_kurucz.new             simulated colours from Kurucz models
magslist_phoenix_grid.new           simulated colours from Phoenix models

A utility code magnitude_transform.py is provided.  It allows one to read in
the simulated magnitudes values and look at different colour-colour plots and
fits to see which combinations may produce good results.  Unlike the main
code, the magnitude_transform.py code can use any filters for any of the
colours and one does not need to read in data values for the code to work.

Also included are some documentation files

readme.txt
jwst_magnitude_conversion.docx

and the files for an example

m31_f814_f160_subset.data   input ACS F814W and WFC3 F160W data from HST
niriss_transformed.txt      output converted NIRISS F115W and F200W magnitudes
hst_to_niriss.cfg           a parameter file to run the example

and finally an alternate blackbody colours file that covers a wider range of
temperature than the usual file

magslist_blackbody_fullrange.new

that can be used with the program if very low temperature sources are of
interest.  The regular blackbody colours file includes simulations for
temperatures from 100000 K to 1000K.  The full range file extends the low
temperature values down to 100 K.

  The examples in the directory are for the NIRISS version of the code not the
current version that is presented here.  Similarly the document is specific to
the NIRISS version although the full JWST version of the code runs exactly the
same way as the NIRISS version.

  The following packages are needed for the code to run:

math
sys
matplotlib
numpy
Tkinter and ttk
astropy
configobj

All of these are widely available packages.  The code is written in Python 2.7.
However it also works in Python 3.

  The NIRCam througputs (total photon covnersion functions) used in the
magnitude calculations are for module A.  The MIRI throughputs were taken from
the STScI MIRI web pages.  These throughput functions may not be entirely up
to date.  The NIRSpec throughputs are calculated from the throughput files that
were delivered to the ETC, dated 

