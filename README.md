# 一.YOLOv5应用
## 1.1 批量检测图片的过程

1.测试数据集和对应标签的放置

（1）权重文件已经训练好

**注：YOLOv3和YOLOv5n\s\m\l\x都可以用YOLOv5调用训练好的权重文件进行测试得到对应的指标**

YOLOv3的权重文件所在目录：/data/wangxiaofei/yolov3-master/runs/train/exp5/weights/best.pt

![image](https://github.com/wangxiaofei2022/YOLO/blob/main/YOLOv3_weight.png)

YOLOv5的权重文件所在目录：

/data/wangxiaofei/yolov5/runs/train/yolov5n/weights/best.pt

/data/wangxiaofei/yolov5/runs/train/yolov5s/weights/best.pt

......

![image](https://github.com/wangxiaofei2022/YOLO/blob/main/YOLOv5_weight1.png)

![image](https://github.com/wangxiaofei2022/YOLO/blob/main/YOLOv5_weight2.png)

CUDA_VISIBLE_DEVICES=6 python val.py --weights "/data/wangxiaofei/yolov5/runs/train/yolov5n/weights/best.pt" --data "/data/wangxiaofei/yolov5/data/DOTA1_0.yaml"
