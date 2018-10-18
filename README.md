## YOLOv3行人检测辅助脚本集

本脚本集合主要是针对YOLOv3的两个主流版本（[AlexeyAB/darknet](https://github.com/AlexeyAB/darknet) & [pjreddie/darknet](https://github.com/pjreddie/darknet)）的脚本辅助集合，主要用途如下：

1. 从VOC2007/VOC2012/COCO等数据集中提取出person类图片，并转换标注；
2. 计算mAP正确率；
3. 从实验的训练日志中提取出loss变化图

## File structure

```
yolo_person_detect
|
│  README.md
│
├─make_yolo_dataset
│  │  helmet_to_yolo.py
│  │  show_voc_xml.py
│  │  show_yolo_label.py
│  │  xml2json.py
│  │  YOLO_coco_label.py
│  │
│  ├─YOLO_VOC2007
│  │      extract_person.py
│  │      voc_label.py
│  │
│  └─YOLO_VOC2007_2012
│          extract_person_2007.py
│          extract_person_2012.py
│          voc_label.py
│
├─yolo_compute_mAP_on_VOC2007
│      reval_voc_py3.py
│      voc_eval_py3.py
│
└─yolo_loss_analyse
    │  analyse.py
    │  result.png
    │
    └─loss
            train1-loss.txt
            xxx.txt
```



## 效果对比

YOLO_mine

![kite-7-final](D:\yolo_person_detect\results_show\kite-7-final.jpg)

YOLO_pj

![kite-pj](D:\yolo_person_detect\results_show\kite-pj.jpg)

