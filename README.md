# Assignment 2: Local Features, Matching and Panorama Stitching

MSAI6330 Computer Vision. The notebook detects local features in two overlapping photos, describes them with **SIFT** and with **raw 11x11 intensity patches**, matches them, estimates a homography with **RANSAC**, and stitches a panorama. It then compares the two descriptors.

## Repository contents

| Path | What it is |
|---|---|
| `Assignment_2.ipynb` | The assignment notebook, one section per task (1 to 8) |
| `Assignment_2.pdf` | The assignment brief |
| `images/left.jpg`, `images/right.jpg` | The two input images |
| `requirements.txt` | Python dependencies |

## Notebook sections

1. Feature detection (Harris corners; SIFT keypoints)
2. Feature description (SIFT 128-D, 11x11 patch 121-D)
3. Descriptor matching (pairwise Euclidean distances)
4. Putative match selection (ratio test, with explanation)
5. Match visualization (side by side with lines)
6. Homography estimation with RANSAC (inlier count, mean squared reprojection error, inlier plot)
7. Panorama creation (canvas sizing, warping, averaging in the overlap)
8. SIFT vs intensity patch comparison, and the conclusion

## Setup

Requires Python 3.10 or newer. From the repository root:

**macOS / Linux**
```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
jupyter notebook Assignment_2.ipynb
```

**Windows (PowerShell)**
```powershell
python -m venv venv
venv\Scripts\Activate.ps1
pip install -r requirements.txt
jupyter notebook Assignment_2.ipynb
```

Then choose **Kernel > Restart & Run All**. Start Jupyter from the repository root, otherwise the notebook cannot find `images/`.

The notebook uses a fixed random seed, so RANSAC results are reproducible. Everything runs on CPU in well under a minute.

## Dependencies

`numpy`, `matplotlib`, `opencv-python` (4.4 or newer, where `cv2.SIFT_create` is in the main package), plus `notebook` and `ipykernel` to run the notebook.
