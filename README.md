# QuantifyPD_1
The quantification of plasmodesmata callose includes two parts and here is part1 that use Fiji Macro to automatically quantify aniline blue signal at plasmodesmata.
Fiji macro
The core backbone of this macro comes from Matt and the basic steps are explained in the attached word file ‘Annalisa callose methods’. 

In addition to the core steps designed by Matt and described in the methods, Annalisa added some features to the macro:

The macro is now formed by two parts, that can be run separately or as one unique analysis process. If you want to run a section, highlight it and hit 'run -> selected code'. If you want to run all, just hit 'run':
PART 1 is designed to split your channels before the callose analysis in case you collect images with another channel together with aniline blue (I needed this part  for my PLUG callose staining, because I had collected also the red channel to be sure the PLUG was well activated in each sample). You won’t need this part if you only have one channel. If you only have one channel per image, just proceed running only PART 2.
PART 2 is the proper callose analysis
There is possibility to select PD based on shape, in order to exclude signals that are coming from very long and thin objects
Possibility to define the extension of the files to process: this is useful if your files are not .czi, for example once you have split your channels the extension it is not .czi anymore but .tif. Remember to adjust this accordingly before the analysis, otherwise the script won’t find your images.
Both sections of the script will now ask you to select an input and output folder in a tiny window that will pop up as soon as you hit run. The input folder is the folder where the script will try and find your images to analyse, the output is where it will save the masks that highlight the detected PD. After you ran your analysis, it is important that you check the mask images by opening them up in fiji to make sure your analysis is correct and you are detecting the desired blobs of signal.
 
In conclusion, to run the Fiji macro you need to:

1. Create an input folder with you images
2. Create an empty folder that will be the output folder
3. Adjust the file extension in the macro to match the one of your images
4. Adjust the parameters of threshold, size and shape (if you like) in order to detect the PD. To find the correct settings for your samples, I suggest that you run a few attempt of analysis with different values of these parameters on a subset of your images. I usually run this on 5 images for each genotype and keep repeating the cycle adjust parameters -> run analysis on subset of images -> check masks of detected PD until I am satisfied with the parameters. I try to find parameters that detect PD in a fair way in all the genotypes of one experiment. For the comparison between genotypes in one experiment to be fair, the parameters chosen for the analysis need to be the same across all samples of the experiment.
Threshold: the script will create a mask that detects only the pixels that are above that threshold value
Maxsize and minsize: the script will count as PD only those particles that are composed of a number of pixels higher than the minsize value and lower than the maxsize value, of course the pixels are counted only if their intensity is above the threshold
A way to have an idea of threshold values that may be good for your samples is to open an image and adjust the brightness and contrast values and check how does the image look like at different values. Another way is to zoom on a PD and place your cursor over a pixel that is part of the PD, the intensity value of that pixel will be displayed on the Fiji interface, under all the buttons.

5. Once your are satisfied with the values of parameters, you can run the analysis on all your images of that experiment. When analysing data from another experiment, remember to first check that the parameters are still fitting well and you get a good detection of PD.
 

All these things to be adjusted are in lines 56-62 of the macro.
