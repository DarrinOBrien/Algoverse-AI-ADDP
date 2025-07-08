Darrin O'Brien, darrinobrien5@gmail.com

The CLIP Model used is directly from OpenAI's CLIP Github: 
- https://github.com/openai/CLIP


This folder fine-tunes and Augments CLIP entirely on the vision side. 
The text encoder is dropped and the visual encoder is the only one used. 
I add a classifier head with classes = num_classes for each dataset.
Fine-tuning fine-tunes both the visual encoder and the classifier head.
Includes all 8 Image Classification Datasets (SUN397, Stanford_Cars, RESISC45, EuroSAT, SVHN, GSTRB, MNIST, and DTD).
The Datasets are from tanganke's Collections on Hugging Face:
- https://huggingface.co/collections/tanganke/the-eight-image-classification-tasks-6644ce0376c0a469f6928507 


Binary classification was only done for the MNIST dataset. Findings:
- All 3 transformations (Affine, Transformation Matrix, Translation Vector) are sufficient. 
- Only one image is needed to achieve full classification accuracy.
- Translation Vector best option as least resources needed for calculations.


Entire Dataset Generalization Done for MNIST. Findings:
- Both Affine and Transformation Matrix are nearly identicle. Translation Vector is Random.
- Focus on Transformation Matrix only for little difference in accuracy compared to Affine