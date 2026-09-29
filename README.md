# Fine-Tuning SAM 2 for Surgical Scene Segmentation

## Overview
This repository contains the code for fine-tuning and evaluating the Segment Anything Model 2 (SAM 2) to enhance its semantic segmentation performance on anatomical tissues/organs in surgical videos/images. The fine-tuned model, **SurgiSAM 2**, demonstrates remarkable accuracy in segmenting organs and tissues, even with limited training data of 50 samples per class.

## Datasets
The following surgical video/image datasets were used:

1. **CholecSeg8k** [1]: Laparoscopic cholecystectomy images.
2. **Dresden** [2]: Colorectal surgery images.
3. **UreterUD** [3]: Urological surgery images.
4. **Endoscapes** [4]: Laparoscopic cholecystectomy images.
5. **m2caiSeg** [5]: Minimally invasive abdominal surgery images.

## Results
- **Zero-shot weighted mean Dice coefficient (WMDC)**: 
  - 0.84 (**Hiera Large**) 
  - 0.78 (**Hiera Base Plus**).
- **Fine tuning** the image encoder and mask decoder (of Base Plus model) improved WMDC to **0.92** (+0.14 - relative increase of 17.9% over baseline).
- **Impact of training data scale** on finetuned model performance:
  - **0.9288** (with 400 samples per class, 10-point prompts).
  - **0.912** (with 50 samples per class, 10-point prompts).
- **Outperformed SOTA** on 24/30 (80%) of all organ classes.
- **Generalization**: Outperformed SOTA on 7/9 (**77.8%**) of unseen organ classes.

## Fine-tuned Model Checkpoints
The fine-tuned SurgiSAM2 model checkpoints are available at:
[https://figshare.com/articles/media/SurgiSAM2_Fine-tuning_a_foundational_model_for_surgical_video_anatomy_segmentation_and_detection/28489961](https://figshare.com/articles/media/SurgiSAM2_Fine-tuning_a_foundational_model_for_surgical_video_anatomy_segmentation_and_detection/28489961)

## License
The code in this repository is licensed under the Apache License 2.0 (see LICENSE).

SurgiSAM2 is built on SAM 2 (https://github.com/facebookresearch/sam2),
Copyright (c) Meta Platforms, Inc. and affiliates, licensed under Apache 2.0.
The fine-tuned checkpoints on Figshare are derived from SAM 2 weights.

## Citation
If you use SurgiSAM2 in your research, please cite our paper published in Scientific Reports:

Kamtam, D.N., Shrager, J.B., Malla, S.D. et al. A fine-tuned foundational model SurgiSAM2 for surgical video anatomy segmentation and detection. Sci Rep 15, 17098 (2025). https://doi.org/10.1038/s41598-025-11759-4

## References

1. [https://arxiv.org/abs/2012.12453](https://arxiv.org/abs/2012.12453)
2. [https://www.nature.com/articles/s41597-022-01719-2](https://www.nature.com/articles/s41597-022-01719-2)
3. [https://www.mdpi.com/1424-8220/24/9/2926](https://www.mdpi.com/1424-8220/24/9/2926)
4. [https://arxiv.org/abs/2212.04155](https://arxiv.org/abs/2212.04155)
5. [https://arxiv.org/abs/2008.10134](https://arxiv.org/abs/2008.10134)
