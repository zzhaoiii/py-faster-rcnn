## 安装依赖
- docker环境：zhy/caffe-frcnn-gpu:latest    
- docker服务器：192.168.16.247  
- 镜像中未含代码，需建立挂载
```
nvidia-docker run -it runtime=nvidia --name=caffe-frcnn -v /home/zhangzhao/project/git/py-faster-rcnn:/home/ zhy/caffe-frcnn-gpu:latest
```
### 准备数据
1.  文件目录组织规范，cd ~/data/VOCdevkit2007/VOC2007
```
|-->JPEGImages(训练集图片)
    |-->原始图像(*.jpg)
|-->ImageSets(数据集列表)
    |-->原始图像(*.jpg)
|-->Annotations （训练集标注）
    |-->(*.xml)
```
2. 自动生成ImageSets下数据集列表，cd ~/data/VOCdevkit2007/
```
python split_data.py -f VOC2007
```
### 使用说明
见 [py-faster-rcnn 训练参数修改](https://www.cnblogs.com/bile/p/9110986.html)