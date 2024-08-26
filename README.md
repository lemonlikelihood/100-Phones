# 100-Phones: A Large VI-SLAM Dataset for Augmented Reality Towards Mass Deployment on Mobile Phones
Visual-inertial SLAM (VI-SLAM) is a key technology for Augmented Reality (AR), which allows the AR device to recover its 6-DoF motion in real-time in order to render the virtual content with the corresponding pose. Nowadays, smartphones are still the mainstream devices for ordinary users to experience AR. However the current VI-SLAM methods, although performing well on high-end phones, still face robustness challenges when deployed on a larger stock of mid- and low-end phones. Existing VI-SLAM datasets use either very ideal sensors or only a limited number of devices for data collection, which cannot reflect the capability gaps that VI-SLAM methods need to solve when deployed on a large variety of phone models. This work proposes 100-Phones. the first VI-SLAM dataset covering a wide range of mainstream phones in the market. The dataset consists of 350 sequences collected by 100 different models of phones. Through analysis and experiments on the collected data, we conclude that the quality of visual-inertial data vary greatly among the mainstream phones, and the current open source VI-SLAM methods still have serious robustness issues when it comes to mass deployment on mobile phones. We release the dataset to facilitate the robustness improvement of VI-SLAM and to promote the mass popularization of AR.  
![Alt text](assets/100phones-teaser.png)

# Video
For the details, you can refer to 
https://www.youtube.com/watch?v=NIlEa_M_aeA

# Our Dataset

## List of 100 phone models
![100-phones-table](./assets/100-phones-table.png)

We design three simple yet typical motions to collect three sub-datasets in a small-scale scene. Each sub-dataset contains 100 sequences collected by the 100 phones. We organize the three sub-dataset as follow and we name the data format as "dior".

## Dataset Format

The format of files are as follow:

### Circle/Line/Rotation 

```shell
eg: train_data/circle/huawei-mate30-pro.tar.xz
|--camera
|   |--images
|     |--6158863991000.jpg
|     |--6158897604000.jpg
|     |--...
|   |--data.csv
|   |--sensor.yaml
|--imu
|   |--data.csv
|   |--sensor.yaml
|--htc
|   |--data.csv
|   |--sensor.yaml
|--groundtruth
|   |--data.csv
|   |--euorc_gt_body.csv
|   |--sensor.yaml

```

### General 
```shell
eg: train_data/general/huawei-mate30-pro/2022-11-21-11-45-19-465-normal-walk-f1.tar.xz
|--camera
|   |--images
|     |--76204892580000.jpg
|     |--76204926193000.jpg
|     |--...
|   |--data.csv
|   |--sensor.yaml
|--imu
|   |--data.csv
|   |--sensor.yaml
|--groundtruth
|   |--euorc_gt_body.csv

```

### "general"

We design the fourth sub-dataset in three large-scale scenes. We select five phones, each collects ten sequences, resulting in 50 sequences. For the "general" sub-dataset, we arrange the data according to five different phone models. Every phone model contains ten sequences of different motions. We organize the "general" sub-dataset as follow:

> general
>
> |-- huawei-mate30-pro (phone-model)
>
> ​    |-- 2022-11-21-11-45-19-465-normal-walk-f1 (sequence-name)
>
> ​	    |-- camera
>
> ​		    |-- sensor.yaml
>
> ​		    |-- data.csv
>
> ​			|-- images
>
> ​                |-- 76204892580000.jpg
>
> ​                |-- 76204926193000.jpg
>
> ​                |-- ...
>
> ​        |-- imu
>
> ​             |-- sensor.yaml
>
> ​             |-- data.csv
>
> ​        |-- groundtruth
>
> ​             |-- euroc_gt_body.csv
>
> ​    |-- 2022-11-21-12-26-08-733-walk-forward-backward-f1 (sequence-name)
>
> ​        |-- ...
>
> |-- vivo-iqoo-7 (phone-model)
>
> ​    |-- ...
>
> | -- ...  

### For ROS

We also provide  the corresponding  bags for VI-SLAM systems that based on ROS. "circle-raw-bag"、“line-raw-bag” and "rotation-raw-bag" contain the raw IMU and image messages.  "circle-sync-bag"、“line-sync-bag” and "rotation-sync-bag" contain the synchronized IMU and image messages with the offline calibrated time offset. Each directory contains bags for 100 model of phones corresponding to the respective motion mode.

For the "general" sub-dataset, "general-raw-bag" and "general-sync-bag" would be also provided and we organized the bags  the same way as before.


# Download
You can download our dataset from following addresses:

https://pan.baidu.com/s/1W1KluP2V77j5HAQwblh0vQ?pwd=n985

# Citation

If you find this code useful for your research, please use the following BibTeX entry.

```bibtex
@article{zhang2024100,
  title={100-Phones: A Large VI-SLAM Dataset for Augmented Reality Towards Mass Deployment on Mobile Phones},
  author={Zhang, Guofeng and Yuan, Jin and Liu, Haomin and Peng, Zhen and Li, Chunlei and Wang, Zibin and Bao, Hujun},
  journal={IEEE Transactions on Visualization and Computer Graphics},
  year={2024},
  publisher={IEEE}
}
```

# Copyright

This work is affiliated with ZJU-SenseTime Joint Lab of 3D Vision, and its intellectual property belongs to SenseTime Group XR.

```
Copyright SenseTime. All Rights Reserved.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```

