# Flood-Detection-Watershed-Segmentation
Flood Detection Watershed Using Otsu thresholding

# Methodology
## 1. Input
RGB flood images
Corresponding ground truth masks
## 2. Preprocessing Pipeline

The following steps are applied to enhance image quality:

### Grayscale Conversion
Reduces image complexity by converting RGB to single-channel intensity.
### Gaussian Blur
Removes noise using a 5×5 kernel.
### CLAHE (Contrast Enhancement)
Improves local contrast, especially in low-light or shadowed areas.
### Otsu Thresholding
Automatically converts image into binary (foreground vs background).
### Morphological Opening
Removes small noise using erosion + dilation.
## 3. Marker Generation

Watershed requires markers:

Sure Background → Generated using dilation
Sure Foreground → Extracted using distance transform
Unknown Region → Background − Foreground
## 4. Watershed Segmentation
Applied using cv2.watershed()
Segments image into regions
Boundaries marked in red
## 5. Output
Binary flood mask
Flood regions highlighted on original image
Boundary visualization
## 6. Evaluation Metrics
Dice Coefficient
IoU (Jaccard Index)
Accuracy, Precision, Recall
