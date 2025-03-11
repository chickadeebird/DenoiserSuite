# Denoiser Suite

This is a Pixinsight script for denoising both linear and nonlinear images. The denoising system was setup to manage the denoising of both linear and nonlinear images similarly. The denoising is based on the training of 3 different convolutional neural networks. There are currently 3 networks included in this suite.

The algorithms should all work both with and without a GPU, although GPU acceleration greatly enhances the speed of the denoisers.

# Algorithm A

This algorithm is the fastest of all the algorithms in this suite, but potentially at very low and very high levels of noise it sometimes incompletely denoises the image.

# Algorithm B

This algorithm is by far the slowest of the algorithms, possibly up to 100 times a slow, but it seems to provide the most accurate estimate of the signal in many instances. It may be prone to smoothing details in high signal areas, so the use of a scaled lightness mask may be helpful to reduce any unwanted signal loss in the high signal areas. The mask function is supplied, but defaults to "<No Mask>".

# Algorithm C

This algorithm is a middle ground in terms of both speed of execution and estimate of the signal.

# Algorithm D

This algorithm seems to be the best all around version of the 4 I have made available and the one that I use most frequently.

# Usage

These algorithms should work on mono and multi-channel/RGB images.

Select Linear data if you wish the algorithm to treat the data as linear, otherwise significant blending artifacts may be seen.

## Uses

The script is used to denoise linear and nonlinear images as well as mono and multi-channel/RGB images.

## Images

This is a nonlinear image of a stack of images on the Iris nebula with an autoSTF applied (top left), the results from algorithm A (top right), algorithm B (bottom left), and algorithm C (bottom right).

<img src="./figs/DenoiserSuite no mask on Iris.png" text='DenoiserSuite script' align=left />

This is a linear image from the Leo triplet using algorithm B. It shows the improvement in detail preservation with a stretched lightness mask applied. Top left - original linear stacked image; top right - stretched lightness mask; bottom left - algorithm B with no mask; bottom right - algorithm B with lightness mask applied to preserve high signal details.

<img src="./figs/DenoiserSuite algorithm B mask.png" text='DenoiserSuite algorithm B with and without mask' align=left />

## Script

This is the script interface for the DenoiserSuite script.

<img src="./figs/DenoiserSuite script.png" text='SyntheticStars script' align=left />  <br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>

This can be found here: ChickadeeScripts > SyntheticStars after installation.

## Manage repository location

In order to automatically install and subsequently refresh script updates in Pixinsight, add the following URL to Resources > Updates > Manage repositories

https://raw.githubusercontent.com/chickadeebird/DenoiserSuite/main/

After this has been added to the repositories, Resources > Updates > Check for updates should place the new DenoiserSuite script in Scripts > ChickadeeScripts

## Machine learning files location

The Denoising Suite script calls an executable file that is a machine learning program trained for the denoising functions for the script. The executable for the Windows version can be downloaded via the following link:

https://drive.google.com/file/d/1TXFU-I7uNb8j4Q6ddg3z9n7UGUOoacRp/view?usp=sharing

The executable for the MacOS version is here (many thanks to pfile on the Pixinsight forums for creating the MacOS version - this is not GPU enhanced and there is a significant startup time):

https://drive.google.com/file/d/1nkrbxVmixpQhMsOAdhDO3uifXQyiKrMR/view?usp=sharing

Place the zip file in a location on your computer and unzip the contents. Start the DenoiserSuite script in Pixinsight under the Scripts > ChickadeeScripts location. Click on the wrench at the bottom left of the DenoiserSuite dialog box and then move to the location where the executable files have been unzippped. The enables the DenoiserSuite script to find the executable in the correct location.
