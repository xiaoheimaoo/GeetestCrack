# GeetestCrack
基于yolov5的极验空间推理模型训练
## 接口加密分析思路
加密参数w的值可以通过参考一些AST反混淆的教程分析js文件。</br>
测试接口：`service-gkzuwk0z-1307225969.bj.apigw.tencentcs.com/release/test`</br>
接口随时都可能会关掉，如果不通就是被我关掉了。</br>
POST请求json格式，返回值即为w的值。
```json
{
  "passtime": "666", #通过验证时间
  "xy": "1234_5442", #点击坐标
  "pic": "/nerualpic/space_l1_zh_2019.07.17/space/d839d79ae9d9b768a869c1a40448ecb3.jpg", #前置请求返回结果中的pic值
  "gt": "c9428d9361cd70d26e28d7cd780ec640", #gt值
  "challenge": "9a5d3a1db9dadbaa867f6a34a5512740", #challenge值
  "c": "[12, 58, 98, 36, 43, 95, 62, 15, 12]", #前置请求返回结果中的c值
  "s": "514c622c" #前置请求返回结果中的s值
}
```
## 验证码问题求解思路
训练模型比较简单，我自己标记了100张图的标签，可以直接训练，也可以直接用我训练好的权重文件`best.pt`，训练了大概700次左右，感觉效果还是不错的，我认为比较麻烦的部分还是分析问题找出符合条件的物体，我写出的逻辑识别成功率大概在80%，暂时不公开逻辑。</br>
`请点击在黄色圆柱体后面的黄色物体。`判断前后左右，可以根据物体底部的xy坐标。</br>
`请点击与绿色物品有相同大小的球。`判断相同大小，可以对比符合条件的物体的二维面积，最相近的可以认为相同大小。</br>

![image](https://raw.githubusercontent.com/xiaoheimaoo/GeetestCrack/master/img/1.jpg)
![image](https://raw.githubusercontent.com/xiaoheimaoo/GeetestCrack/master/img/2.jpg)
![image](https://raw.githubusercontent.com/xiaoheimaoo/GeetestCrack/master/img/3.jpg)
![image](https://raw.githubusercontent.com/xiaoheimaoo/GeetestCrack/master/img/4.jpg)
## 免责声明

**该项目仅用于学术交流，不得任何商业使用！**
