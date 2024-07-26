# MUSHROOM CLASSIFICATION AI

This model swiftly identifies various mushrooms for users using image recognition technology, enabling rapid analysis of different mushrooms based on their distinct features. Many deaths have been reported due to the misidentification of mushrooms as those used in everyday cooking and those that are deadly. This assists people in identifying a handful of mushrooms to promote the public interest in fungi exploration through AI innovation.

The species that the AI can detect are:
- Agaricus Augustus (Edible)
- Amanita Muscaria (Poisonous)
- Amanita Phalloides (Deadly)
- Armillaria Mellea (Edible)
- Flammulina Velutipes (Edible)
- Galerina Marginata (Deadly)
- Grifola Frondosa (Edible)
- Laccaria Ochropurpurea (Edible)
- Lycoperdon Perlatum (Edible)
- Mycena Leaiana (Inedible)
- Omphalotus Illudens (Poisonous)
- Suillus Luteus (Edible)
- Trametes Gibbosa (Inedible)
- Tylopilus Fellus (Inedible)
- Volvopluteus Gloiocephalus (Edible)

<img width="1080" alt="Screenshot 2024-07-26" src="https://github.com/user-attachments/assets/a893adec-6eea-49e4-a2ae-ff3f44b8493a">

## The Algorithm

The algorithm works though ResNet-18. It is a retrained model processed on a database of a handful of species from Kaggle found here: https://drive.google.com/drive/folders/1T5EkuFzoUcHmQwJiqkJ6RPwOdLPVesdY?usp=sharing
(original database of the images found here: https://www.kaggle.com/code/gauravduttakiit/mushrooms-images-classification/input).

## Running this project

1. Make sure that the Jetson Inference library and Python3 are installed onto your Jetson Nano
2. Download the resnet18.onnx from here: https://drive.google.com/file/d/1nJQ_zokjQnc0We8meOpn65rSyyjDxecM/view?usp=sharing
3. Download the dataset from Google Drive found here: https://drive.google.com/drive/folders/1T5EkuFzoUcHmQwJiqkJ6RPwOdLPVesdY?usp=sharing
4. Open the terminal to navigate to the classification directory:
`cd jetson-inference/python/training/classification`
5. Set the net and dataset variables:
`NET=models/mushroom_classification_15_v2 `
`DATASET=data/mushroom_classification_15`
6. Run the command for the AI to process the image. The second last argument can be any input image of your choice to be addressed, and the last argument specifies what you want the output file to look like (**NOTE:** To specify files that contain spaces, they must be surrounded with "quotation marks" to address the file.)
`imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/"Agaricus Augustus (Edible)"/"Agaricus augustus_274.jpg" mushroom_classified.jpg`

![Screenshot 2024-07-26 20921](https://github.com/user-attachments/assets/6288b476-72e8-42db-b9ac-2401812a8379)

**NOTE FOR FUTURE REFERENCE:** Due to project deadlines, the image recognition software is only limited to 15 out of the millions of different fungi species that exist. This project is open sourced and can be trained on more classes if wanted!

[Video Demonstration of the Mushroom Classification AI](https://www.youtube.com/watch?v=0RndZ4bSutI)
