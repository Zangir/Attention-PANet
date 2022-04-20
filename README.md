# Attention-PANet
This is an implementation of [Attention PANet for Object Detection in Aerial Images](https://arxiv.org/pdf/1803.01534.pdf). The model generates bounding boxes and segmentation masks for each instance of an object in the image. It's based on [mattport Mask RCNN](https://github.com/matterport/Mask_RCNN) which using keras and tensorflow.

![Instance Segmentation Sample](assets/street.png)



## Example commands to launch the project
conda config --append channels conda-forge

conda create -n dl_proj13 python=3.5

conda activate dl_proj13

pip install --upgrade pip

pip install -r requirements.txt 

conda install -c conda-forge gcc

pip install git+https://github.com/philferriere/cocoapi.git#subdirectory=PythonAPI

python setup.py install

git clone https://github.com/matterport/Mask_RCNN

pip install --upgrade prompt-toolkit==2.0.1

pip3 install --upgrade --force jupyter-console

download mask_rcnn_coco.h5 (https://github.com/matterport/Mask_RCNN/releases/download/v2.0/mask_rcnn_coco.h5) and put it to logs/ folder



## Useful commands

### Navigate project
conda activate dl_proj13

cd Documents/DL_proj/tensor_panet/

### First run with downloading COCO data
python3 samples/coco/coco.py train --dataset='COCO_data' --model='logs/mask_rcnn_coco.h5' --download=True

### From the second run
python3 samples/coco/coco.py train --dataset='COCO_data' --model='logs/mask_rcnn_coco.h5' --download=False

### Evaluate model
python3 samples/coco/coco.py evaluate --dataset='COCO_data' --model='logs/mask_rcnn_coco.h5' --download=False



## Useful links

### PANet
https://github.com/ryanzhangfan/PA-Net

### mrcnn demo
https://github.com/matterport/Mask_RCNN/blob/master/README.md
