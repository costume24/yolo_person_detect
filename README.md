## YOLOv3行人检测

本脚本集合主要是针对YOLOv3的两个主流版本（[AlexeyAB/darknet](https://github.com/AlexeyAB/darknet) & [pjreddie/darknet](https://github.com/pjreddie/darknet)）的脚本辅助集合，主要用途如下：

1. 从VOC2007/VOC2012/COCO等数据集中提取出person类图片，并转换标注；

2. 计算mAP正确率；

3. 从实验的训练日志中提取出loss变化图

## 文件结构

```
yolo_person_detect
|
│  README.md
│
├─make_yolo_dataset
│  │  helmet_to_yolo.py                     # 某次比赛用到的转换代码
│  │  show_voc_xml.py                       # 可视化VOC数据集
│  │  show_yolo_label.py                    # 可视化YOLO数据集
│  │  xml2json.py                           # 
│  │  coco_to_yolo.py                       # COCO --> YOLO
│  │
│  ├─YOLO_VOC2007                           # VOC2007
│  │      extract_person.py                 # 从VOC2007数据集中提取person图片
│  │      voc_label.py                      # 将提取到的person图片转为YOLO格式
│  │
│  └─YOLO_VOC2007_2012                      # VOC2007 + VOC2012
│          extract_person_2007.py
│          extract_person_2012.py
│          voc_label.py
│
├─yolo_compute_mAP_on_VOC2007               # 在VOC2007上测试性能
│      reval_voc_py3.py
│      voc_eval_py3.py
│
└─yolo_loss_analyse
    │  analyse.py                           # 训练过程可视化代码
    │  result.png                           # 可视化训练过程
    └─loss
            train7-loss.txt                 # 示例训练日志
```

## 效果对比



YOLO_mine（只检测行人）

![kite-7-final](https://github.com/pascal1129/yolo_person_detect/blob/master/results_show/kite-7-final.jpg)

YOLO_pj（官版，全检测）

![kite-pj](https://github.com/pascal1129/yolo_person_detect/blob/master/results_show/kite-pj.jpg)



## 数据集统计

数据集        | 训练集（person）| 测试集（person）
----------------| ---|---
VOC2007   | 5011（2095）  |4952（2097）
VOC2012   | 17125（4374）|未统计
COCO2017| 118287（64115）|未统计

\* 括号里面为person类图片数量



## 训练过程

数据集：VOC2007+VOC2012+COCO2017

硬件环境：GTX1080ti*2, Ubuntu16.04

训练迭代数：8w iters

训练技巧：参见[how-to-train-to-detect-your-custom-objects](https://github.com/AlexeyAB/darknet#how-to-train-to-detect-your-custom-objects)



![训练过程](https://github.com/pascal1129/yolo_person_detect/blob/master/yolo_loss_analyse/result.png)