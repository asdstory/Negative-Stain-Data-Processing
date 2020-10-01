*Using RELION version 3.1.0.

## Step00: Convert file format


```sh
module load EMAN2/2.22
e2proc2d.py *.dm3 @.mrc
#for .tif, if you see sigma=0 warning,do following to force the convert:
e2proc2d.py *.tif @.mrc --writejunk
```

## Step01: Import
### Movies/mics

Import raw movies/micrographs? Yes

Raw input files: 500*.tif

Are these multi-frame movies? No

Optics group name: opticsGroup1

MTF of the detector:

Pixel size (Angstrom): 2.5  (T12 old camera US4000)

Voltage (kV): 120

Spherical aberration (mm): 1.2

Amplitude contrast: 0.1

Beamtilt in X (mrad): 0

Beamtilt in Y (mrad): 0

## Step02: Manual Picking

Display?

## Step02: Autopicking using Gautomatch

```sh
Gautomatch --apixM 2.5 --diameter 200 --speed 1  --lsigma_cutoff 5  --lave_min -1.0  --cc_cutoff 0.2  *.mrc --gid 0  --dont_invertT
```

## Step03: Extract particle

### extract

Invert contrast? No

## Step04: 2D classification

## Step05: Select template from above 2D class for autopicking 

## Step06: AutoPick

## Step07: Extract particles again

## Step08: 2D classification

