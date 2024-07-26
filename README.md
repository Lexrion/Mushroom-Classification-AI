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

![Screenshot of the AI's Demonstration](https://drive.google.com/file/d/1l8M82AHlcESv1cY0P1TOXKq4AU3r5jpY/view?usp=sharing)

## The Algorithm

The algorithm works though ResNet-18. It is a retrained model processed on a database of a handful of species from Kaggle found here: https://drive.google.com/drive/folders/1T5EkuFzoUcHmQwJiqkJ6RPwOdLPVesdY?usp=sharing
(original database of the images found here: https://www.kaggle.com/code/gauravduttakiit/mushrooms-images-classification/input).

## Running this project

1. Make sure that the Jetson Inference library and Python3 are installed onto your Jetson Nano
2. Download the resnet18.onnx from here: https://drive.google.com/file/d/1nJQ_zokjQnc0We8meOpn65rSyyjDxecM/view?usp=sharing
3 Open the terinal to navigate to the classification directory:
`cd jetson-inference/python/training/classsification`
4. Download the dataset from Google Drive found here: https://drive.google.com/drive/folders/1T5EkuFzoUcHmQwJiqkJ6RPwOdLPVesdY?usp=sharing
4. Set the net and data variables:
`NET=models/mushroom_classification_15_v2 `
`DATASET=data/mushroom_classification_15`
5. Run the command for the AI to process the image. The second last argument can be any input image of your choice to be addressed, and the last argument specifies what you want the output file to look like (**NOTE:** To specify files that contain spaces, they must be surrounded with "quotation marks" to address the file.)
`imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/"Agaricus Agustus (Edible)"/"Agaricus agustus_274.jpg" mushroom_classified.jpg`

**NOTE FOR FUTURE REFERENCE:** Due to project deadlines, the project is only limited to 15 out of the millions of different fungi species that exist

[Video Demonstration of the Mushroom Classification AI](video link)
