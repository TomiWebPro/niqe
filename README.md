# Modern Python support - NIQE
# Modification by nuniniyujin
* The original implementation is from : https://github.com/guptapraful/niqe
* There were big discrepancy between Matlab NIQE score and the original python implementation :
* Extracted clean image's mean & cov from matalb (data/clean_image_parameters.mat) and added minor modifications
* After modification (NIQE score below:)

| Image                     | Python version | Matlab (NIQE) |
|---------------------------|----------------|---------------|
| bikes.bmp                  | 3.298          | 3.231         |
| bikes_distorted.bmp        | 8.057          | 8.037         |
| parrots.bmp                | 3.778          | 3.789         |
| parrots_distorted.bmp      | 5.607          | 5.613         |

# Modification by TomiWebPro
* Modified upon https://github.com/nuniniyujin/niqe/tree/score_debug
* The nuniniyujin niqe.py had mulitiple import issues due to many of the pip packages falled out of scope. The current modification uses .npz file instead of .mat and provides a requirement.txt so code can be downloaded and deployed more quickly.
* The 2nd modification produces the same result as the python version above.
* The .mat files in the data folder are only for legacy purposes, it is not used by niqe.py at all. It can be safely removed if dev desire. 

# About NIQE
NIQE (Completely blind image quality assessment) for grayscale images using skvideo's NIQE.

# How to run?
On windows, download zip and extract, ensure there is data folder.

```python
from PIL import Image
import numpy as np
from niqe import calculate_niqe

# Path to your PNG image
image_path = './test_imgs/sample.png'

# Compute NIQE score
score = calculate_niqe(image_path)

print(f"NIQE score: {score:.3f}")
```
