# DETR 
Welcome to our Computer Vision project.

**Abstract.** In this work, we introduce the panoptic segmentation problem of image, its evaluation metric, and provide the 2020 SOTA Detection Transformer (DETR) as the optimal solution. Then explain explicitly how does DETR performs object detection: the Transformer architecture, the process of extracted image's feature transformation to Transformer's digestible form, the queries for questioning detected object and the loss computation, also the optimization algorithm. In order to deploy panoptic segmentation, the panoptic head is added to notice each detected object and render the segmentation version of image. Finally, we clarify its powerful properties by implement [COCO-2017](https://cocodataset.org/index.htm#download) pretrained model and apply it to solve [Wheat Head detection problem](https://www.kaggle.com/c/global-wheat-detection).

**Keywords**: detection, segmentation, detr, global-wheat-detection.

:star: For the detail of our report, see [Approaching Object detection and Panoptic segmenation problem by DETR](https://github.com/thoconvuive/DETR/blob/main/DETR.pdf).

:star: Slide of report can be found [here](https://docs.google.com/presentation/d/1KwgIYg5b5bM0LvTm2xkX046GSgFxpU45/edit?usp=sharing&ouid=114052551064589379844&rtpof=true&sd=true).

:star: Pre-trained model can be found [here](https://www.kaggle.com/tranviethoang/best-model).

:star: We add the code-only version of [Wheat head dataset EDA](https://github.com/hoangtv2000/DETR_for_wheat_dectection/blob/main/wheat_head_EDA.ipynb). You can try yourself by running the script. 


# Notebooks
+ For the implementation of COCO-2017 pretrained model. We install and demonstrate its performance by plotting the prediction (included visualization of attention mechanism). The work can be found at [Implement pretrained DETR for object detection and panoptic segmentation](https://github.com/thoconvuive/DETR/blob/main/Implement%20pretrained%20DETR%20for%20object%20detection%20and%20panoptic%20segmentation.ipynb)  

+ We train the pre-trained DETR model to get a prediction of wheat in Wheat Head dataset. This is a really hard problem, our training model have a acceptable result. See [Implement DETR for Wheat detection](https://github.com/thoconvuive/DETR/blob/main/Implement%20DETR%20for%20Wheat%20detection.ipynb) for full detail.

### Update
+ We add [hand-craft annotation](https://github.com/thoconvuive/DETR/blob/main/_annotations.csv) of the test images, build an mAP evaluation metric and test on it.
+ We train a new DETR by freezing pre-trained backbone (the whole backbone/part of the backbone) for wheat detection task above, sadly it got worse result (evaluate by mAP) :sweat_smile:. So we keep the best model as the un-frozen model.



## Result

**Object detection of wheat in Wheat Head dataset**

<p float="left">
  <img src="https://github.com/hoangtv2000/DETR_for_wheat_dectection/blob/main/results/res1.jpg" />
  <img src="https://github.com/hoangtv2000/DETR_for_wheat_dectection/blob/main/results/res2.jpg" /> 
  <img src="https://github.com/hoangtv2000/DETR_for_wheat_dectection/blob/main/results/res3.jpg" width="273" />
</p>

**Our mAP scores**

Result on **confident threshold**: **0.9**

|No. image| AP       |No. image| AP   |
|-------- |----------|---------|------|
|1        |  0.345   |6        |0.148|
|2        |  0.467   |7        |0.636|
|3        |  0.431   |8        |0.407|
|4        |  0.529   |9        |0.514|
|5        |  0.391   |10       |0.493|
|**mAP**  | **0.4365**              |||
