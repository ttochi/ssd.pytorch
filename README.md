# On-device project
Code base: https://github.com/amdegroot/ssd.pytorch

## Requirement

Create conda env:
```
conda create -n ssd python==3.8
pip install torch==1.13.0+cu117 torchvision==0.14.0+cu117 torchaudio==0.13.0 --index-url https://download.pytorch.org/whl/cu117
pip install opencv-python
pip install numpy==1.23.1
```

Download VOC2007 dataset:
```
cd data
mkdir datasets && cd datasets
curl -LO http://host.robots.ox.ac.uk/pascal/VOC/voc2007/VOCtest_06-Nov-2007.tar
tar -xvf VOCtest_06-Nov-2007.tar
```

Download model weight:
```
mkdir weights
wget https://s3.amazonaws.com/amdegroot-models/ssd300_mAP_77.43_v2.pth
```

## Run evaluation
```
python eval.py --voc_root=$REPOSITORY/data/datasets/VOCdevkit
```
