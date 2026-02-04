# MMLS_v2
We present MMLSv2, a dataset for landslide segmentation on Martian surfaces. MMLSv2 consists of multimodal imagery with seven bands: RGB, digital elevation model, slope, thermal inertia, and grayscale channels. MMLSv2 comprises 664 images distributed across training, validation, and test splits. 


> **Dataset download:** [link here](<https://drive.google.com/file/d/1O5KltZxRiQ6mR1qk4pbu4AprAxc-t8rS/view?usp=sharing>)

---

## Band order

| Band | Description |
|------|-------------|
| B1   | Red         |
| B2   | Green       |
| B3   | Blue        |
| B4   | DEM         |
| B5   | Slope       |
| B6   | Thermal inertia |
| B7   | Grayscale   |

---

## Image stats and format

- **Shape:** `(128, 128, 7)`
- **Dtype:** `float32`
- **Channels:** `7`
- **Value range:** `0.0` to `1.0`

---

## Mask stats and format

- **Shape:** `(128, 128)`
- **Dtype:** `uint8`
- **Channels:** `1` (grayscale)
- **Unique values:** `[0, 1]`
- **Value range:** `0` to `1`
