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

（2）测试集放置

根据/data/wangxiaofei/yolov5/data/DOTA1_0.yaml里面设置路径

![image](https://github.com/wangxiaofei2022/YOLO/blob/main/path.png)

**/data/wangxiaofei/yolov5/data/images/下面分别有train、val、test三个文件，文件下又有images和labels两个文件夹**

![image](https://github.com/wangxiaofei2022/YOLO/blob/main/test_path.png)

上图中，labels.cache是运行val.py文件后产生的；images文件夹里存放需要测试的图片；labels里存放对应的yolo的txt标签

![image](https://github.com/wangxiaofei2022/YOLO/blob/main/yolo_txt_label.png)

2.运行过程

（1）运行val.py文件，其中两行修改为如下

**parser.add_argument('--task', default='test', help='train, val, test, speed or study')**

**parser.add_argument('--project', default=ROOT / 'runs/val', help='save to project/name')**

（2）YOLOv5运行语句如下

**CUDA_VISIBLE_DEVICES=6 python val.py --weights "/data/wangxiaofei/yolov5/runs/train/yolov5n/weights/best.pt" --data "/data/wangxiaofei/yolov5/data/DOTA1_0.yaml"**

**CUDA_VISIBLE_DEVICES=6 python val.py --weights "/data/wangxiaofei/yolov5/runs/train/yolov5s/weights/best.pt" --data "/data/wangxiaofei/yolov5/data/DOTA1_0.yaml"**

**CUDA_VISIBLE_DEVICES=6 python val.py --weights "/data/wangxiaofei/yolov5/runs/train/yolov5m/weights/best.pt" --data "/data/wangxiaofei/yolov5/data/DOTA1_0.yaml"**

**CUDA_VISIBLE_DEVICES=6 python val.py --weights "/data/wangxiaofei/yolov5/runs/train/yolov5l/weights/best.pt" --data "/data/wangxiaofei/yolov5/data/DOTA1_0.yaml"**

**CUDA_VISIBLE_DEVICES=6 python val.py --weights "/data/wangxiaofei/yolov5/runs/train/yolov5x/weights/best.pt" --data "/data/wangxiaofei/yolov5/data/DOTA1_0.yaml"**

生成的结果在/data/wangxiaofei/yolov5/runs/val/exp1文件夹下

（2）YOLOv3运行语句如下

**CUDA_VISIBLE_DEVICES=6 python val.py --weights "/data/wangxiaofei/yolov3-master/runs/train/exp5/weights/best.pt" --data "/data/wangxiaofei/yolov5/data/DOTA1_0.yaml"**

# 二.YOLOv2应用
## 2.1 批量检测图片的过程

