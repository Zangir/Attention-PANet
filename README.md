# Attention-PANet
This is an implementation of Attention PANet for Object Detection in Aerial Images. The model generates bounding boxes and segmentation masks for each instance of an object in the image. It's based on [mattport Mask RCNN](https://github.com/matterport/Mask_RCNN) which using keras and tensorflow. The difference is three functions : AttentionModule, SpatialAttention and ChannelAttention in MaskRCNN class in mrcnn/model.py file. All dependencies are mentioned in the requirements.txt.

![Instance Segmentation Sample](assets/street.png)



## Commands to prepare the project
conda config --append channels conda-forge

conda create -n dl_proj13 python=3.5

conda activate dl_proj13

pip install --upgrade pip

git clone https://github.com/Zangir/Attention-PANet.git

pip install -r requirements.txt 

conda install -c conda-forge gcc

pip install git+https://github.com/philferriere/cocoapi.git#subdirectory=PythonAPI

cd Attention-PANet/

python setup.py install

git clone https://github.com/matterport/Mask_RCNN

pip install --upgrade prompt-toolkit==2.0.1

pip3 install --upgrade --force jupyter-console

download mask_rcnn_coco.h5 (https://github.com/matterport/Mask_RCNN/releases/download/v2.0/mask_rcnn_coco.h5) and put it to logs/ folder



## Useful information

The main file is samples/coco/coco.py used for both training and evaluation. It uses MaskRCNN class in mrcnn/model.py, which is implementation of basic PANet model. By default it uses COCO, but iSaid and any other dataset can be provided in separate folder and mentioned as --dataset='path_data' while running coco.py. Demo.txt file shows input commands to train and evaluate COCO dataset and corresponding outputs.

### Navigate project
conda activate dl_proj13
cd Attention-PANet/

### First run with downloading COCO data
python3 samples/coco/coco.py train --dataset='COCO_data' --model='logs/mask_rcnn_coco.h5' --download=True

### From the second run
python3 samples/coco/coco.py train --dataset='COCO_data' --model='logs/mask_rcnn_coco.h5' --download=False

### To evaluate the model
python3 samples/coco/coco.py evaluate --dataset='COCO_data' --model='logs/mask_rcnn_coco.h5' --download=False



## Useful links

### PANet
https://github.com/ryanzhangfan/PA-Net

### mrcnn demo
https://github.com/matterport/Mask_RCNN/blob/master/README.md
