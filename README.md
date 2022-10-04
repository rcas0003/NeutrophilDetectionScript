# NeutrophilDetectionScript

This script has been developed as a Python Macro for FIJI, to assist with the process of data collection from light microscopy images of microfluidic infection-on-a-chip devices. 
It is designed to detect the number of neutrophils recruited to the microchamber. It uses the Laplacian of Gaussian detector from the TrackMate Plugin, but bypasses some of the processing-heavy tracking steps.

The following factors can be adjusted:
- Size of the ROI
  
  *yolk = OvalRoi(0, 0, 180, 180)*
  
  The height and width of the ROI is determined by the 3rd and 4th numbers listed. This can be altered by adjusting the 180 up or down. 
- The radius and threshold used for neutrophil detection
  
  *settings.detectorSettings = {
        'DO_SUBPIXEL_LOCALIZATION': True,
        'RADIUS': 2.5,
        'TARGET_CHANNEL': 1,
        'THRESHOLD': 5.,
        'DO_MEDIAN_FILTERING': False,
    }*
  
  The expected radius and the threshold of this radius can be adjusted to alter what objects within the image are detected as neutrophils. It is suggested that this adjustment process is completed using TrackMate manually first, and the determined values are supsequently input into the script.
