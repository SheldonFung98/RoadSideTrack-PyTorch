# RoadSideTrack-PyTorch
vision-based lane &amp; side tracking algorithm (train code included) written in Python with PyTorch using fscn model.

## Installation
Clone this repository:
```
git clone https://github.com/SheldonFung98/RoadSideTrack-PyTorch
```

## Usage
### Train
Link the checkpoint & dataset folder to the root of this repository.
```
ln -s /path/to/your/checkpoint_folder checkpoints
ln -s /path/to/your/datasets_folder datasets
```
The structure of `datasets` folder should be as follows:
```
datasets
    - cityscapes
        - gtFine
            - train
                1_gtFine_labelIds.png
                2_gtFine_labelIds.png
                ...
            - test
                ...
            - val
                ...
        - leftImg8bit
            - train
                1.png
                2.png
                ...
            - test
                ...
            - val
                ...
```
* The data images in `leftImg8bit` should be RGB image.
* The label image in `gtFine` should be three channel mask image. 
* Configurations can be edit in `configs/cityscapes_fast_scnn.yaml`.

Now you can train your model with the following command:
```
python3 tools/train.py
```
### Run

You can see the segmentation result via running the provided python script.

## Inference with TensorRT
Please check [this repo](https://github.com/SheldonFung98/RoadSideTrack)
