# 第三方库安装
```powershell
pip install numpy matplotlib pillow wordcloud imageio jieba snownlp itchat -i https://pypi.tuna.tsinghua.edu.cn/simple
```
# 常用参数

- width 词云图片宽度，默认400像素

- height 词云图片高度 默认200像素

- background_color 词云图片的背景颜色，默认为黑色

  `background_color='white'`

- font_step 字号增大的步进间隔 默认1号

  font_path 指定字体路径 默认None，对于中文可用`font_path='msyh.ttc'`

- mini_font_size 最小字号 默认4号

- max_font_size 最大字号 根据高度自动调节

- max_words 最大词数 默认200

- stop_words 不显示的单词 `stop_words={"python","java"}`

- Scale 默认值1。值越大，图像密度越大越清晰

- prefer_horizontal：默认值0.90，浮点数类型。表示在水平如果不合适，就旋转为垂直方向，水平放置的词数占0.9？

- relative_scaling：默认值0.5，浮点型。设定按词频倒序排列，上一个词相对下一位词的大小倍数。有如下取值：“0”表示大小标准只参考频率排名，“1”如果词频是2倍，大小也是2倍

- mask 指定词云形状图片，默认为矩形

  通过以下代码读入外部词云形状图片（需要先`pip install imageio`安装imageio）
  
```python
w = wordcloud.WordCloud(      
    width=400,
    height=200,
    background_color='black',
    font_path=None, 
    font_step=1,
    min_font_size=4,
    max_font_size=None,
    max_words=200,
    stopwords={},
    scale=1,
    prefer_horizontal=0.9,
    relative_scaling=0.5,
    mask=None) 
```
  

# 词云绘制
**Num.1**
```powershell
# 导入词云制作第三方库wordcloud
import wordcloud

# 创建词云对象，赋值给w，现在w就表示了一个词云对象
w = wordcloud.WordCloud()

# 调用词云对象的generate方法，将文本传入
w.generate('How delightful it is to have friends coming from afar. Welcome to my knowledge planet.')

#将生成的词云保存为output1.png图片文件，保存出到当前文件夹中
w.to_file('output1.png')
```
![Output1](https://raw.githubusercontent.com/HuangFengjue/mdimages/main/output1.png)

需要注意的是，wordcloud库会非常智能地按空格进行分词及词频统计，出现次数多的词就大。如果输入的是“欢迎大家来到我的首页。”这样完整的句子就无法被绘制成词云，需要用到之后会讲到的jieba库。

**Num.2**
```powershell
import wordcloud

w = wordcloud.WordCloud(width = 1000, height = 700, background_color = 'white', font_path='msyh.ttc')

w.generate('从明天起，做一个幸福的人。喂马、劈柴，周游世界。从明天起，关心粮食和蔬菜。我有一所房子，面朝大海，春暖花开')

w.to_file('output2.png')
```
![Output1](https://raw.githubusercontent.com/HuangFengjue/mdimages/main/output2.png)


**Num.3**
```python

```
