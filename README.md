# Denoiser Suite

This is a Pixinsight script for denoising both linear and nonlinear images. The denoising system was setup to manage the denoising of both linear and nonlinear images similarly. The denoising is based on the training of 3 different convolutional neural networks. There are currently 3 networks included in this suite.

# Algorithm A

This algorithm is the fastest of all the algorithms in this suite, but potentially at very low and very high levels of noise it sometimes incompletely denoises the image.

# Algorithm B

This algorithm is by far the slowest of the algorithms, possibly up to 100 times a slow, but it seems to provide the most accurate estimate of the signal in many instances. It may be prone to smoothing details in high signal areas, so the use of a scaled lightness mask may be helpful to reduce any unwanted signal loss in the high signal areas. The mask function is supplied, but defaults to "<No Mask>".

# Algorithm C

This algorithm is a middle ground in terms of both speed of execution and estimate of the signal.

# Usage

These algorithms should work on mono and multi-channel/RGB images.

Select Linear data if you wish the algorithm to treat the data as linear, otherwise significant blending artifacts may be seen.

## Uses

The script is used to denoise linear and nonlinear images as well as mono and multi-channel/RGB images.

## Images

This is a sample pair of an original image (left), and an image where the stars are replaced with synthetic stars (right).

<img src="./figs/SyntheticStars replaced.png" text='Synthetic stars script - left original stars, right replaced with synthetic stars' align=left />

<img src="./figs/SyntheticStars kept.png" text='Synthetic stars script - left original stars, right synthetic starfield created' align=left />

## Script

This is the script interface for the SyntheticStars script.

<img src="./figs/SyntheticStars script.png" text='SyntheticStars script' align=left />

This can be found here: ChickadeeScripts > SyntheticStars after installation.

## Manage repository location

In order to automatically install and subsequently refresh script updates in Pixinsight, add the following URL to Resources > Updates > Manage repositories

https://raw.githubusercontent.com/chickadeebird/SyntheticStars/main/

After this has been added to the repositories, Resources > Updates > Check for updates should place the new SyntheticStars script in Scripts > ChickadeeScripts

## Machine learning files location

The Denoising Suite script calls an executable file that is a machine learning program trained for the denoising functions for the script. The executable can be downloaded via the following link:

https://drive.google.com/file/d/1ez7cz05RAwoPX9-Dn_mpSFqBUhzoVDV-/view?usp=sharing

Place the zip file in a location on your computer and unzip the contents. Start the DenoiserSuite script in Pixinsight under the Scripts > ChickadeeScripts location. Click on the wrench at the bottom left of the DenoiserSuite dialog box and then move to the location where the executable files have been unzippped. The enables the DenoiserSuite script to find the executable in the correct location.
