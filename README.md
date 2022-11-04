# docker4ceres
We developed a new implementation of CERES (Collection of Elemental Routines for Echelle Spectra, [Brahm et al 2017](https://ui.adsabs.harvard.edu/#abs/2017PASP..129c4002B/abstract)) using a DockerFile allowing professional astronomers and students to reduce the sbectra taken using FIDEOS (FIber Dual Echelle Optical Spectrograph, [Tala et al., 2014](https://ui.adsabs.harvard.edu/abs/2014SPIE.9147E..89T/abstract)) throught the agreement TUCAN-1 (Telescopio Universidad Católica- Universidad de Antioquia 1 metro).

# Authors:

### Original

 Rafael Brahm, Andrés Jordán, Néstor Espinoza. [Brahm et al 2017](https://ui.adsabs.harvard.edu/#abs/2017PASP..129c4002B/abstract).


### This version
 
  Dr. Germán Chaparro-Molano ([saint-germain](https://github.com/saint-germain)), Computational Physics and Astrophysics Group (FACom) Institute of Physics, University of Antioquia Medellin, Colombia.\
  Natalia Alvarez-Baena ([nataliaalvarezb](https://github.com/nataliaalvarezb)), Institute of Physics, University of Antioquia Medellin, Colombia.\
  Dr. Ricardo Carrera ([carrerajimenez](https://github.com/carrerajimenez)), INAF-Osservatorio Astronomico di Padova, vicolo dell'Osservatorio 5, 35122 Padova, Italy.


# About the code

This new version aims to fix the portability issues of installing locally the pipeline allowing students and researchers to use it without risking their  computers. This version also allows to reduce spectra that is not linked to a source available in [SIMBAD](https://simbad.unistra.fr/simbad/) as is the case for sky spectra.

# Requirements

This version was tested for macOS with M1 chip and for Ubuntu

# Usage

1. Download the folder ceres with the files ceres.DockerFile.ubuntu, ceres.DockerFile.mac and requirements.txt
2. Delete the .mac or .ubuntu from the DockerFile depending on your Operative System.
3. Open a terminal and once you are inside the ceres folder type

```
sudo docker build -t ceres -f ceres.Dockerfile .
```
  Make sure you include the final dot.

4. Verify that the DockerFile was installed using

```
sudo docker image list
```

5. Run the DockerFile typing

```
sudo docker run -p 8888:8888 ceres
```

6. In your browser open

```
sudo docker run -p 8888:8888 ceres
```
7. Open a terminal in JupyterLab and type

```
/bin/bash
```
8. Install CERES with

```
python install.py
```
9. Run the pipeline following the instructions on the README of the [original](https://github.com/rabrahm/ceres) version or the [modified](https://github.com/TUCAN1/ceresUdeA) one.
