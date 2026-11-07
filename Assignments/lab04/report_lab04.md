# Lab Report — Lab 04: Watershed Segmentation

*Answer each question briefly and factually — a number, a name, or a short phrase is enough.
Each question is marked on whether the required information is present and correct, not on how
it's written, so there is no benefit to writing full sentences or extra explanation.*

**Q1.** In Step 1 (`colour_channel`), which colour channel is subtracted from the red channel?
Answer: Blue(channel 2).Step 1 is red minus blue.

**Q2.** Which OpenCV function did you use in Step 1 to subtract one channel from the other?
Answer: cv2.subtract

**Q3.** Apart from `cv2.THRESH_OTSU`, which flag did you pass to `cv2.threshold` in Step 2
(`threshold`)?
Answer: cv2.THRESH_BINARY(cv2.TRESH_BINARY+cv2.THRESH_OTSU)

**Q4.** How many dilation iterations (`dilate_iterations`) does Step 4 (`background_mask`) use?
Answer: 10 (dilate_iterations defaults to 10)

**Q5.** Which OpenCV function computes the distance map in Step 5 (`distance_transform`)?
Answer: cv2.distanceTransform

**Q6.** Which function did you use in Step 6 (`orange_markers`) to find the local maxima of the
distance map?
Answer: peak_local_max (from skimage.feature)

**Q7.** What `peak_spacing` value did you use in Step 6?
Answer: 40 (peak_spacing default)

**Q8.** In Step 6, in which order do you pass a peak's coordinates to `cv2.circle` — `(row, col)`
or `(col, row)`?
Answer: (col, row). cv2.circle takes (x, y), which is (col, row), so you pass (int(col), int(row)).

**Q9.** In Step 8 (`create_markers`), what label value is given to the unknown region?
Answer: 0 (the unknown region is set to 0 so watershed decides it)

**Q10.** In Step 9 (`apply_watershed`), which image is passed to `cv2.watershed` — the colour image
or the binary image?
Answer : The colour image (cv2.watershed(image, markers.copy()))
