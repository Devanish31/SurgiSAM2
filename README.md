Fine-Tuning SAM 2 for Surgical Scene Segmentation

Overview
This repository contains the code for fine-tuning and evaluating the Segment Anything Model 2 (SAM 2) to enhance its semantic segmentation performance on anatomical tissues/organ in surgical videos/images. The fine-tuned model, SurgiSAM 2, demonstrates remarkable accuracy in segmenting organs and tissues, even with limited training data of 50 samples per class.

Datasets
The following surgical video/image datasets were used:
1.	CholecSeg8k [1]: Laparoscopic cholecystectomy images.
2.	Dresden [2]: Colorectal surgery images.
3.	UreterUD [3]: Urological surgery images.
4.	Endoscapes [4]: Laparoscopic cholecystectomy images.
5.	m2caiSeg [5]: Minimally invasive abdominal surgery images.

Results
•	Zero-shot weighted mean Dice coefficient (WMDC): 0.84 (Hiera Large) and 0.78 (Hiera Base Plus).
•	Fine tuning the image encoder and mask decoder (of Base Plus model) improved WMDC to 0.92 (+0.14 - relative increase of 17.9% over baseline)
•	Impact of training data scale on finetuned model performance: 0.9288 (with 400 samples per class, 10-point prompts) and 0.912 (with 50 samples per class, 10-point prompts).
•	Outperformed SOTA on 24/30 (80%) of all organ classes.
•	Generalization - Outperformed SOTA on 7/9 (77.8%) of unseen organ classes.

References:
1.	https://arxiv.org/abs/2012.12453
2.	https://www.nature.com/articles/s41597-022-01719-2
3.	https://www.mdpi.com/1424-8220/24/9/2926
4.	https://arxiv.org/abs/2212.04155
5.	https://arxiv.org/abs/2008.10134
