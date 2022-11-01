# GeetestCrack
基于yolov5的极验空间推理模型训练
## 测试接口
加密参数w的值可以通过参考一些AST反混淆的教程分析js文件。</br>
测试接口：`http://49.234.3.186:8888/index`</br>
接口随时都可能会关掉，如果不通就是被我关掉了。</br>
### GET请求参数
参数  |   值 |
---- | ---- |
gt	  | c9428d9361cd70d26e28d7cd780ec640 |
challenge    | 9a5d3a1db9dadbaa867f6a34a5512740 |

### 请求成功示例
```json
{
  "msg":[],
  "result":"success",
  "score":"1",
  "validate":"ac00fdb3bc74b012c3b82cca057675fa" #使用challenge和validate一起提交验证即可
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
