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

![add image descrition here](direct image link here)

## The Algorithm

The algorithm works though ResNet-18. It is a retrained model processed on a database of a handful of species from Kaggle found [here](https://drive.google.com/drive/folders/1T5EkuFzoUcHmQwJiqkJ6RPwOdLPVesdY?usp=sharing) (original database of the images found [here](https://www.kaggle.com/code/gauravduttakiit/mushrooms-images-classification/input)).

## Running this project

1. Make sure that the Jetson Inference library and Python3 are installed onto your Jetson Nano
2. Download the resnet18.onnx from the repository
3 Open the terinal to navigate to the classification directory:
`cd jetson-inference/python/training/classsification`
4. Set the net and data variables:
`NET=models/mushroom_classification_15_v2 `
5.    imagenet.py --model=$NET/resnet18.onnx --input_blob=[image here] --output_blob=[output filename here] --labels=$DATASET/labels.txt $DATASET/test/

**NOTE FOR FUTURE REFERENCE:** Due to technical limitations during the training process from memory allocation, the model has only trained for 27 epochs having low accuracy.

[Video Demonstration of the Mushroom Classification AI](video link)
