# Record-Thresholding

## Name
Thamizh S

## Register Number
212224040350

## Objective

Implement and compare different image thresholding techniques using OpenCV.

The techniques used are:

- Global Thresholding
- Adaptive Thresholding
- Otsu's Thresholding

## Requirements

- Python 3
- OpenCV (`cv2`)
- NumPy
- Matplotlib
- Input image: `exp8img.jpg`

## Methodology

1. Import the required Python libraries.
2. Read the input image.
3. Convert the image from BGR to grayscale.
4. Apply Global Thresholding with a threshold value of `127`.
5. Apply Adaptive Gaussian Thresholding.
6. Apply Otsu's Thresholding to automatically determine the optimal threshold.
7. Display the original image and the thresholded results for comparison.

## Implementation

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread("exp8img.jpg")

gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

_, global_thresh = cv2.threshold(
    gray, 127, 255, cv2.THRESH_BINARY
)

adaptive_thresh = cv2.adaptiveThreshold(
    gray,
    255,
    cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
    cv2.THRESH_BINARY,
    11,
    2
)

_, otsu_thresh = cv2.threshold(
    gray,
    0,
    255,
    cv2.THRESH_BINARY + cv2.THRESH_OTSU
)

plt.figure(figsize=(10, 8))

plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(img, cv2.COLOR_BGR2RGB))
plt.title("Original Image")
plt.axis("off")

plt.subplot(2, 2, 2)
plt.imshow(global_thresh, cmap="gray")
plt.title("Global Thresholding")
plt.axis("off")

plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresh, cmap="gray")
plt.title("Adaptive Thresholding")
plt.axis("off")

plt.subplot(2, 2, 4)
plt.imshow(otsu_thresh, cmap="gray")
plt.title("Otsu's Thresholding")
plt.axis("off")

plt.tight_layout()
plt.show()
```

## Output



### Original Image

<img width="221" height="256" alt="image" src="https://github.com/user-attachments/assets/92ae8f94-041c-47b2-9ccf-5211f106c79a" />

### Global Thresholding

<img width="256" height="286" alt="image" src="https://github.com/user-attachments/assets/a1c95209-2621-485a-9aa9-0307aa985e7f" />

### Adaptive Thresholding

<img width="275" height="299" alt="image" src="https://github.com/user-attachments/assets/f0955779-060f-4cbc-886c-51f71de99399" />

### Otsu's Thresholding

<img width="188" height="285" alt="image" src="https://github.com/user-attachments/assets/b64430d1-ae84-40f1-a417-d12520d325b8" />
