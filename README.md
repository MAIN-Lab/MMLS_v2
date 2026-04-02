# MMLSv2: A Multimodal Dataset for Martian Landslide Detection in Remote Sensing Imagery

<p align="center">
<img src="./images/fig_1_2.png" width="100%"/>
</p>

## Announcements

- MMLSv2 is available for download via Google Drive
- MMLSv2 has been accepted at the 4th Workshop on AI for Space (AI4Space) @ CVPR 2026 📣📣📣
- MMLSv2 preprint is available on [arXiv](https://arxiv.org/abs/2602.08112)
- MMLSv2 is the official dataset for the 1st Mars Landslide Segmentation Challenge (MARS-LS) at the [22nd IEEE/CVFPerception Beyond the Visible Spectrum Workshop](https://pbvs-workshop.github.io/challenge.html) @ CVPR 2026. 
  
## Summary

We present MMLSv2, a dataset for landslide segmentation on Martian surfaces. MMLSv2 consists of multimodal imagery with seven bands: RGB, digital elevation model, slope, thermal inertia, and grayscale channels. MMLSv2 comprises 664 images distributed across training, validation, and test splits. In addition, an isolated test set of 276 images from a geographically disjoint region from the base dataset is released to evaluate spatial generalization. 

## Paper

The preprint of MMLSv2 is available at [arXiv](https://arxiv.org/abs/2602.08112).

## Dataset download

The dataset is available for download via Google Drive [here](https://drive.google.com/drive/folders/1K0PgbDmaHtiA_iQD9mLhRY85Mh8zW0VT?usp=sharing) 

## Dataset description

### Splits and statistics

The distribution of the **MMLSv2** dataset across the different splits is summarized below. The foreground ratio (FG) is expressed as the percentage of pixels belonging to landslide regions, including its average (Avg. FG), standard deviation (Std. FG), and minimum–maximum values (Min. FG, Max. FG).

| Split         | # Images | Avg. FG (%) | Std. FG (%) | Min. FG (%) | Max. FG (%) |
|---------------|----------|-------------|-------------|-------------|-------------|
| Train         | 465      | 35.41       | 25.64       | 0.02        | 99.52       |
| Val           | 66       | 31.53       | 24.05       | 0.08        | 90.32       |
| Test          | 133      | 33.82       | 25.05       | 0.10        | 90.67       |
| Isolated test | 276      | 21.83       | 17.08       | 0.01        | 71.95       |

### Band order

The **MMLSv2** dataset consists of seven bands, each representing different spectral or derived information used for analysis. The bands are ordered as follows:

| Band | Description |
|------|-------------|
| B1   | Red         |
| B2   | Green       |
| B3   | Blue        |
| B4   | DEM         |
| B5   | Slope       |
| B6   | Thermal inertia |
| B7   | Grayscale   |

<img src="./images/sample_images_mmlsv2.png" width="75%"/>

### Image stats and format

Each sample in the dataset is represented as a multi-channel image with the following characteristics:

- **Shape:** `(128, 128, 7)`
- **Dtype:** `float32`
- **Channels:** `7`
- **Value range:** `0.0` to `1.0`

### Mask stats and format

Each mask in the dataset corresponds to a single-channel annotation map with the following characteristics:

- **Shape:** `(128, 128)`
- **Dtype:** `uint8`
- **Channels:** `1` (grayscale)
- **Unique values:** `[0, 1]`
- **Value range:** `0` to `1`

## Benchmarking results

### Base test set

The following table reports the performance of different segmentation models evaluated on the **base test set** of the MMLSv2 dataset.

| Method        | Precision | Recall | F1-score | IoU_BG | IoU_FG | mIoU | Inference time (s) | Training time (h) |
|---------------|------------|----------|------------|----------|----------|--------|---------------------|--------------------|
| U-Net         | 0.858      | 0.868    | 0.863      | 0.868    | 0.759    | 0.814  | **0.005**           | 0.088              |
| U-Net++       | 0.864      | 0.879    | 0.871      | 0.875    | 0.772    | 0.823  | 0.011               | 0.085              |
| PSPNet        | 0.866      | 0.884    | 0.875      | **0.878**| 0.778    | 0.828  | **0.005**           | **0.027**          |
| DeepLabV3     | **0.870**  | 0.860    | 0.865      | 0.872    | 0.763    | 0.817  | 0.007               | 0.063              |
| DeepLabV3+    | 0.863      | **0.889**| **0.876**  | **0.878**| **0.779**| **0.829**| 0.007             | 0.048              |
| SegFormer     | 0.859      | 0.863    | 0.861      | 0.867    | 0.756    | 0.812  | 0.041               | 0.131              |

### Isolated test set

The following table reports the performance of different segmentation models evaluated on the **isolated test set** of the MMLSv2 dataset.

| Method        | Precision| Recall| F1-score| IoU_BG| IoU_FG| mIoU| Inference time (s) |
|---------------|------------|----------|------------|----------|----------|--------|---------------------|
| U-Net         | 0.676      | 0.828    | 0.744      | 0.848    | 0.593    | 0.721  | **0.007**           |
| U-Net++       | 0.701      | 0.743    | 0.722      | 0.851    | 0.564    | 0.708  | 0.020               |
| PSPNet        | 0.679      | 0.786    | 0.729      | 0.846    | 0.573    | 0.709  | 0.008               |
| DeepLabV3     | **0.727**  | 0.754    | 0.740      | **0.862**| 0.588    | 0.725  | 0.016               |
| DeepLabV3+    | 0.699      | 0.714    | 0.706      | 0.847    | 0.546    | 0.696  | 0.014               |
| SegFormer     | 0.684      | **0.856**| **0.761**  | 0.855    | **0.614**| **0.735**| 0.080             |

## License

Distributed under MIT license. See `LICENSE` for more information.

## Citation

If you find this dataset useful, please star ⭐️⭐️⭐️ our repo and cite our paper.

```bibtex
@InProceedings{mmlsv2_2026,
  title={MMLSv2: A Multimodal Dataset for Martian Landslide Detection in Remote Sensing Imagery},
  author={Paheding, Sidike and Reyes-Angulo, Abel and Ramos, Leo Thomas and Sappa, Angel D. and Rajaneesh, A. and Hiral, P. B. and Sajin Kumar, K. S. and Oommen, Thomas},
  booktitle={Proceedings of IEEE/CVF Computer Vision and Pattern Recognition (CVPR) Workshops},
  year={2026}
}
```

## Contact

Sidike Paheding - Fairfield University, USA - spaheding@fairfield.edu

Abel Reyes-Angulo - Michigan Technological University, USA - areyesan@mtu.edu

Leo Thomas Ramos - Computer Vision Center, Universitat Autònoma de Barcelona, Spain - ltramos@cvc.uab.cat

Angel D. Sappa - Computer Vision Center, Universitat Autònoma de Barcelona, Spain - asappa@cvc.uab.cat

