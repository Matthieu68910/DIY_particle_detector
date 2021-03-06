<img align="right" src="https://github.com/ozel/DIY_particle_detector/raw/master/images/Alpha-spectrometer_with_ceramics_in_chocolate_box.jpeg" width="400">

*Corresponding scientific article:* [![DOI](https://img.shields.io/badge/doi-10.3390/s19194264-blue.svg?style=flat&labelColor=grey)](https://doi.org/10.3390/s19194264)

*Repository archive on Zenodo:* [![DOI](https://img.shields.io/badge/doi-10.5281/zenodo.3361755-blue.svg?style=flat&labelColor=grey)](https://doi.org/10.5281/zenodo.3361755)


# DIY Particle Detector

**Short summary video on twitter**<br>
:point_right: https://twitter.com/CERN/status/1260600298206302210

A mobile low-cost spectrometer for measuring ionising radiation like alpha particles and electrons (energy range: 33 keV to 8 MeV).
It's an educational tool and citizen science device made for exploring natural and synthetic sources of radioactivity such as stones, airborne radon, potassium-rich salt or food and every-day objects (Uranium glass, ceramics, old Radium watches etc.).

## How does it work?
Tiny amounts of electrical charge are generated in repurposed photodiodes by impinging particles. The charges form currents which are amplified and converted into voltage pulses that are compatible with audio/microphone signal inputs.
The size of the pulse is proportional to the energy deposited by the ionising radiation. A reference calibration with sources of known energy spectra is provided.

<img align="right" src="https://github.com/ozel/DIY_particle_detector/raw/master/images/pulse_rain.png" width="300">

A superposition of several recorded pulse waveforms from electrons of beta decays (KCl salt sample, more info below) is shown on the right. This is the raw analog ouput signal of the detector.

Black lines in the upper area represent electronic noise, detected signal pulses from the natural radioactivity of potassium (isotope K-40) are highlighted in red.

<br>

<br>

<br>

<img align="right" src="https://github.com/ozel/DIY_particle_detector/raw/master/images/Alpha_spectrum_Majolika_ceramic.png" width="300">

The energy spectrum on the right - derived from the size of signal pulses - was taken from an old ceramics pendant of the Majolika manufacture (Karlsruhe/Germany) - without vacuum pump, in normal ambient air! 

The characteristic alpha energies of the uranium isotopes are about 1 MeV lower than the actual values due to internal absorption caused by the transparent surface coating on top of the orange uranium-based glaze. More detais on the energy calibration below and in the [paper](https://doi.org/10.3390/s19194264).

<br>

<br>

## Hardware

<img src="https://github.com/ozel/DIY_particle_detector/raw/master/hardware/V1.1/documentation/DIY_Particle_Detector_in_candy-tin-box.jpg" height="350"><img src="https://github.com/ozel/DIY_particle_detector/raw/master/hardware/V1.1/documentation/DIY_Particle_Detector_in_cast-aluminium-case.jpg" height="350">
<img src="https://github.com/ozel/DIY_particle_detector/raw/master/hardware/V1.2/documentation/Alpha_spectrometer_in_candy_box_open.jpg" height="313"><img src="https://github.com/ozel/DIY_particle_detector/raw/master/hardware/V1.2/documentation/Alpha_spectrometer_in_candy_box_closed.jpg" height="313">

The open hardware design files are relased under the CERN Open Hardware Licence.
### Detector Variants
The [schematic drawing](https://github.com/ozel/DIY_particle_detector/blob/master/hardware/V1.2/documentation/DIY%20particle%20detector%20schematic%20v1-2.pdf) contains remarks for using the same circuit board with two partially different sets of components (assembly variants):

* ***Alpha-spectrometer*** measuring energies of alpha particles and electrons using one BPX61 diode.<br/>
  <img src="https://github.com/ozel/DIY_particle_detector/raw/master/hardware/V1.2/documentation/3D_top_alpha.png" height="200"><img src="https://github.com/ozel/DIY_particle_detector/raw/master/hardware/V1.2/documentation/3D_bottom_alpha.png" height="200"><br/>
  After the glass window of the diode is carefully broken-up and removed, it can sense alpha particles (see close-up pictures below). 
  The circuit works most precise with only one BPX61 diode (lowest electronic noise) and was specificaly tuned for this scenario.
  * [get parts & circuit board via kitspace](https://kitspace.org/boards/github.com/ozel/diy_particle_detector/diy%20alpha%20spectrometer/)
  * [parts overview & assembly guide](https://github.com/ozel/DIY_particle_detector/blob/master/hardware/V1.2/documentation/DIY%20detector%20-%20parts%20overview%20v1-2%20alphaspectrometer%20version.pdf)
  * [scientific article incl. reference energy calibration](https://doi.org/10.3390/s19194264)



* ***Electron/beta radiation detector*** measuring mostly electrons (plus few gamma photons) with four very low-cost BPW34F or BPW34FA diodes (<1 EUR each).<br/>
  <img src="https://github.com/ozel/DIY_particle_detector/raw/master/hardware/V1.2/documentation/3D_top_electron.png" height="200"><img src="https://github.com/ozel/DIY_particle_detector/raw/master/hardware/V1.2/documentation/3D_bottom_electron.png" height="200"><br/>
  This variant is not able to detect alpha particles but is  easier to operate (less sensitive to visible light and electromagnetic interference, see section on general requirements below). It is also more sensitive towards sources of low intensity (low rate of radioactive decays) since it has four times the sensor volume compared to using only one diode as sensor. This version is ideal for beginners, in total only 8 components are different compared to the alpha-spectrometer variant above. This assembly variant is similar to the [previous circuit version 1.1](https://github.com/ozel/DIY_particle_detector/tree/master/hardware/V1.1).
  * [get parts & circuit board via kitspace](https://kitspace.org/boards/github.com/ozel/diy_particle_detector/diy%20electron%20detector/)
  * [parts overview & assembly guide](https://github.com/ozel/DIY_particle_detector/blob/master/hardware/V1.2/documentation/DIY%20detector%20-%20parts%20overview%20v1-2%20electron%20version.pdf) 


Both kinds of diodes, the BPW34 series in various plastic cases and the BPX61 with metal casing, have the same sensitive area (~7 mm^2). The physics of these sensors when used for ionizing radiation is explained in detail in the [article corresponding to this repository](https://doi.org/10.3390/s19194264). The section about figure 1 discusses why their general efficiency for detecting gamma photons is quite low.  

Mircoscope image of Osram BPX61 diode below on the left, the green scale indicates 2 mm. The sensitive area of the silicon chip is 2.65 x 2.65 mm^2. A bond wire from the anode pin on the right connects the top of the chip (this side is also marked with a notch in the metal case, lower right corner). 
Care must be taken in order to keep the bond wire in place when the glass window is removed: The right picture shows the mounted BPX61 diode after its glass windows was removed by cutting small dents into the border of the TO metal case with small pliers to crack the glass.

<img src="https://github.com/ozel/DIY_particle_detector/raw/master/hardware/V1.2/documentation/BXP61_mircoscope.png" height="300"><img src="https://github.com/ozel/DIY_particle_detector/raw/master/hardware/V1.2/documentation/BPX61_onboard.jpg" height="300">


### General Requirements

* An absolutely light-tight and electromagnetically shielding metal case is mandatory. Either a commercial one made of die casted aluminium (thick metal provides better immunity towards vibrations and prevents "microphonic effects") or an upcycled tin box for candies. 
  See pictures above and the schematics for corresponding part numbers of specific aluminium cases that fit.
* 9 V battery. NIMH-type accumulators with a nominal value of 9.6 V work best (mains-connected power supplies would introduce too much noise, always use batteries)
* Signal output is in the range of +/- 1 V and compatible with an audio/microphone input such as a headset connector of a mobile phone or laptop (or an oscilloscope if available)
* <img src="https://github.com/ozel/DIY_particle_detector/raw/master/images/low-cost_usb_audio_interfaces.jpg" width="300">

  For higher precision and better reproducability of measurements, a small USB soundcard (< 10 EUR) is recommended:
  The ICY-BOX IB-AC527 on the left and the K&ouml;nig Electronic CMP-SOUNDUSB12 on the right ("3D Sound Controller 5.1") use both a chip series from C-Media Electronics Inc: 
  [CM108](https://www.cmedia.com.tw/products/USB20_FULL_SPEED/CM108AH).
  It's well specified with a flat frequency response in the required 1-5 kHz range and good signal to noise ratio. As standard USB Audio Class devices, no dirvers are required and they are recognised as regular audio input device in many operating systems, including Android & iOS.
* Several reference measurements are provided in [data_analysis_and_reference_measurements/diode_detector/data](https://github.com/ozel/DIY_particle_detector/tree/master/data_analysis_and_reference_measurements/diode_detector/data). 
  All have been recorded using the blue CM108 USB soundcard from König, sampling the input signal (yellow connector) @ 48 kHz and 16 bit resolution.
* The connection cable should use a 3-pin 3.5 mm mini-jack connector since these sound interfaces supply a bias voltage on the ring/center tap of the microphone input which must be circumvented/avoided. 
  For further details please refer to the schematics.

### Detector Signals of Radioactivity on an Oscilloscope 
The screenshots below show typical output signals from both detector variants with arrows highlighting the signal and noise properties. The blue lines represent signals from individual particles, the grey lines are superpositions of earlier particle signals which triggered the oscilloscope as well. For better comparison, a beta & gamma radiation source (potassium salt, KCL) was used in both cases which does not emit alpha particles. The negative pulse with its steep downward edge is the main signal and is larger than the electronic noise. The trigger level must be set well below the noise range, which depends on the intensity of surrounding *electromagnetic interference* (EMI) radiation and stray light reaching into the shielding case of the detector. The short negative main signal pulse is followed by a wider positive overshoot which is proportional in size to the amplitude of the main signal. The overshoot is an effect of the amplifier circuit and also depends on the impedance matching from the detector output to the input of the measurement device. The employed oscilloscope features a default input impedance of 1 megaohm. Microphone and line-in inputs of sound cards (as described above) have considerably lower input impedances and pulse measurements will therefore show a larger signal overshoot. The alpha-spectrometer circuit was intentionally designed to produce this kind of a bi-polar signal with a lot of overshoot in order to mimic actual audio waves.

* ***Electron-Detector***
  ![](images/oscilloscope_pulse_electron-detector.png)
  Main signal amplitudes can be typically well distinguished from electronic noise at about -50 mV (and lower) if the detector is well shielded against light and with low EMI (e.g. no cell phone or electro motor close by). The negative pulses are about 50 to 75 us wide with this circuit.
  

* ***Alpha-Spectrometer***
  ![](images/oscilloscope_pulse_alpha-spectro.png)
  Typical signal amplitudes of particles from the same beta/gamma radiation source are much lower compared to the electron-detector varaint. The electronic noise is much smaller as well and the width of pulses is between 1 and 2 ms. This circuit is optimised for large pulses from alpha particles which is heavy-ionizing radiation and therefore produces a lot more free charges in the sensor. The amplitude threshold which allows to distinguish between electrons (=smaller signal amplitude) and alpha particles (=larger signal amplitude) is at -8 mV in case of a typical oscilloscope with an input impedance of 1 megaohm. This threshold is lower in case of a sound card due to their lower input impedances. Please refer to [the scientific article](https://doi.org/10.3390/s19194264) for detailed information about the energy calibration in this case. 
  
If a hardware oscilloscope is not at hand, a **simple software oscilloscope** with good trigger funtionallity for sound cards and audio inputs of computers can be found here:
https://github.com/ozel/WaveWatch/
To run this program written in Processing, download Version 3 from www.processing.org and install the missing ‘Minim’ library via the ‘Sketch’ menu / ‘Import Library...’ / ‘Add Library...’.
Download my version of the WaveWatch Processing sketch from https://github.com/ozel/WaveWatch/archive/master.zip, unzip and open the file WaveWatch-master/WaveWatch/WaveWatch.pde in Processing.
For more sophisticated processing of the particle signals from radioactive objects like recording their energy spectrum please refer to the [software](#software) section below.

### DIY Detector Building Workshops

These particle detectors have been built by high school students (age 16 - 18) and citizen science enthusiasts (age ~20 - 60) during several workshops.
After a little introduction into the soldering of electronic components, the whole device can be built in less than two hours - including the modification of a candy tin box as its case.

* [S'Cool LAB Summer Camp 2017](https://indico.cern.ch/event/570855/timetable/) at CERN, [poster presentation](https://indico.cern.ch/event/570855/contributions/2616929/attachments/1504724/2344411/RG3_DIY_Detector.pdf)
* [Student Summer School of Barcelona Technoweek 2017](http://icc.ub.edu/congress/TechnoWeek2018/outreach_EN.php), [CERN news](https://home.cern/news/news/knowledge-sharing/summer-school-secondary-students-spain)
* [S'Cool LAB Summer Camp 2018](https://indico.cern.ch/event/726779/timetable/) at CERN, [poster presentation, page 3](https://indico.cern.ch/event/726779/contributions/2991390/attachments/1697186/2732121/pdfjoiner.pdf)
* [Gathering of Open Science Hardware 2018 in Shenzhen China](http://openhardware.science/gatherings/gosh-2018-2/), [workshop documentation](https://forum.openhardware.science/t/day-3-build-your-own-particle-detector-discover-natural-radioactivity/1468)

## Software
The software in this repository is provided under the open source BSD Licence.

It consists of two parts:
* Measurement recording, real-time display and counting of particle pulses
* Data analysis of recorded measurements, providing calibrated energy spectra and time series histograms

### Recording Software
Two kinds of software for recording the voltage pulses are developed:

* A [web browser application](https://ozel.github.io/DIY_particle_detector/data_recording_software/webGui/) based on the Web Audio API of modern browsers (recent Chrome and Firefox versions work best), compatible with mobile/smartphone and desktop operating systems.
  For further notes on its implementation and usage please refer to [pulse_recorder.js](https://github.com/ozel/DIY_particle_detector/blob/master/data_recording_software/webGui/js/pulse_recorder.js). 
  <img src="https://github.com/ozel/DIY_particle_detector/raw/master/images/webGui_screenshot.png" alt="A single pulse recorded by the web browser GUI." width="600">

* A [python script](https://github.com/ozel/DIY_particle_detector/blob/master/data_recording_software/pulse_recorder.py). Ideal for longer measurements, e.g. over night. The reference measurements listed below have been taken with this software.

### Data Analysis

The recorded pulse data is saved in files (using Python's Pickle or the MessagePack format) by the software listed above and opened for further analysis by [analyse_and_plot_pulses.py](https://github.com/ozel/DIY_particle_detector/blob/master/data_analysis_and_reference_measurements/diode_detector/analyse_and_plot_pulses.py).
This python script converts the measurement data into time series histograms and calibrated energy spectra.

## Reference measurements and plots

Several reference measurements have been taken and stored in [data_analysis_and_reference_measurements/diode_detector/data](https://github.com/ozel/DIY_particle_detector/tree/master/data_analysis_and_reference_measurements/diode_detector/data).
If this whole respository is cloned using git, the [git LFS](https://help.github.com/en/articles/duplicating-a-repository#mirroring-a-repository-that-contains-git-large-file-storage-objects) extension must be used to get as well the large data files (~ 1 GB).
The data files can be downloaded alternatively from this [Zenodo data archive](https://doi.org/10.5281/zenodo.3361764).

Overview on reference measurements:

* A mixed alpha source featuring Gd-148, Pu-239, Am-241 & Cm-244 with a combined alpha energy spectrum of 3 to 6 MeV
* 10 g of KCl (potassium chlorid) salt (an alternative to NaCl table salt) as an example for detection of electrons from beta-decays (from naturally occuring K-40)
* a small columbite stone (containing trace amounts of uranium ore), a combined source of electrons and alphas (and gamma photons which do not interact enough within the thin diode detector to be relevant)
* a watch hand from an old watch that was painted with luminescent radium paint. Featuring Ra-226 and all it's radioactive progeny isotopes

## Pixel Detector

For comparsion, two measurements have been made with the [iPadPix](https://github.com/ozel/iPadPix) mobile device that is based on the 1.4 x 1.4 cm^2 hybrid pixel detector Timepix. It's silicon sensor chip area is 28 times larger and the sensitive volume is about 6 times bigger (300 um vs. 50 um) than a single BPW34 or BPX61 diode.
Due to it's larger area, it is well suited for measuring less concentrated sources of radioactivity such as airborne radon progeny collected with an electrostatically charged party balloon.
The diode-based detector can be regarded as a functional model for one pixel of pixel detectors. The physics behind signal formation and subsequent signal processing methods which amplify, characterise and digitise the pulses are the same.
For further details please consult the scripts provided in [data_analysis_and_reference_measurements/pixel_detector](https://github.com/ozel/DIY_particle_detector/tree/master/data_analysis_and_reference_measurements/pixel_detector) and refer to the [corresponding article](https://doi.org/10.3390/s19194264).

## Diode Characterisation

C-V curves of several diodes of the BPW34 series and BXP61 type have been taken to characterise the thickness of the sensitive layer under reverse bias conditions.
With about 8 V on the cathode, the typical sensitive layer thickness is about 50 um which corresponds well with the recorded energy spectra. 
Based on the C-V curves, the following doping profiles are derived:

<img src="https://github.com/ozel/DIY_particle_detector/raw/master/images/Neff_10diodes_HR.png" width="550">

The effective charge carrier concentration 'Neff' is on average about half of the value reported in 2008 by [Ravotti et al.](http://cds.cern.ch/record/1169276/files/04636908.pdf) which can be explained by manufacturing process variations. The similarity of the curve shapes confirms that the investigated diodes use either the same or at least very similar silicon chips. The regular micropattern visible in the doping profile curves is a measurement artefact which is caused by internal rounding errors of the C-V measurement device. The thin double lines indicate the error range of the instrument as stated by its manufacturer (Keysight B1500A with the MFCMU module). 

Further discussion of the CV measurements can be found in [corresponding article](https://doi.org/10.3390/s19194264).
The folder [data_analysis_and_reference_measurements/diode_detector/diode_characterisation_and_simulation_plots](https://github.com/ozel/DIY_particle_detector/tree/master/data_analysis_and_reference_measurements/diode_detector/diode_characterisation_and_simulation_plots) provides the scripts to reproduce the corresponding plots.
The raw C-V measurement data is available in [data_analysis_and_reference_measurements/diode_detector/data/high_resolution_CV](https://github.com/ozel/DIY_particle_detector/tree/master/data_analysis_and_reference_measurements/diode_detector/data/high_resolution_CV).
