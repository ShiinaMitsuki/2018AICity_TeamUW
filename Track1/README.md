# Track 1

## Introduction

Traffic Flow Analysis - Participating teams submit results for individual vehicle speed for a test set containing 27 1-minute videos. Performance is evaluated based on ground truth generated by a fleet of control vehicles that were driven during the recording. Evaluation for Challenge Track 1 is based on detection rate of the control vehicles and the root mean square error of the predicted control vehicle speeds.

## How It Works

In SCT, our loss function consists of motion, temporal and appearance attributes. Especially, a histogram-based adaptive appearance model is designed to encode long-term appearance change for enhanced robustness. The change of loss is incorporated with a bottom-up clustering strategy for the association of tracklets. Robust 2D-to-3D backprojection is achieved with EDA optimization applied to camera calibration for speed estimation. 

## Code structure

Under the `./Track1/` folder, there are 6 software packages:

1. `VDO2IMG_IPL`: Converting each video file to a folder of frame images
2. `CAM_CAL_IPL`: Manual camera calibration based on minimization of reprojection error and EDA optimization
3. `YOLO_VEH_IPL`: Extension of the YOLOv2 object detector with our trained model for vehicle detection/classification
4. `TC_tracker`: Proposed tracklet-clustering-based tracking method
5. `APP_MDL_IPL`: Extraction of histogram-based adaptive apperance models and their comparison
6. `SPD_EST_IPL`: Speed estimation based on input of tracking results and camera parameters

Detailed description of each package is given in each subfolder. 