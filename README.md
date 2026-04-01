# MMLS_v2

We present MMLSv2, a dataset for landslide segmentation on Martian surfaces. MMLSv2 consists of multimodal imagery with seven bands: RGB, digital elevation model, slope, thermal inertia, and grayscale channels. MMLSv2 comprises 664 images distributed across training, validation, and test splits.

> 🏆 **Challenge:** This dataset is currently used in the **Martian Landslide Segmentation Challenge**. You can participate and submit your models here:  
> [**Click here to view the Competition on Codabench**](https://www.codabench.org/competitions/12305/?secret_key=77a18ac3-b954-4eea-804b-987a5c9bf944)

> **Dataset download:** [link here](<https://drive.google.com/drive/folders/1K0PgbDmaHtiA_iQD9mLhRY85Mh8zW0VT?usp=sharing>)
![MMLSv2 Dataset Sample](images/fig_1_2.png)

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

---

## Citation

If you use this dataset in your research or participate in the challenge, please cite the following paper:

```bibtex
@article{mmlsv2_2026,
  title={MMLSv2: A Multimodal Dataset for Martian Landslide Detection in Remote Sensing Imagery},
  author={Paheding, Sidike and Reyes-Angulo, Abel and Ramos, Leo Thomas and Sappa, Angel D. and Rajaneesh, A. and Hiral, P. B. and Sajin Kumar, K. S. and Oommen, Thomas},
  journal={Proceedings of IEEE/CVF Computer Vision and Pattern Recognition (CVPR) Workshop on AI4Space},
  year={2026}
}
