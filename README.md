# 第三方库安装
```powershell
pip install numpy matplotlib pillow wordcloud imageio jieba snownlp itchat -i https://pypi.tuna.tsinghua.edu.cn/simple
```

# 词云绘制
**Num.1**
```powershell
# 导入词云制作第三方库wordcloud
import wordcloud
# 创建词云对象，赋值给w，现在w就表示了一个词云对象
w = wordcloud.WordCloud()
# 调用词云对象的generate方法，将文本传入
w.generate('and that government of the people, by the people, for the people, shall not perish from the earth.')
将生成的词云保存为output1.png图片文件，保存出到当前文件夹中
w.to_file('output1.png')
```

**Num.2**
```powershell
import wordcloud
w = wordcloud.WordCloud(width = 1000, height = 700, background_color = 'white', font_path='msyh.ttc')
w.generate('从明天起，做一个幸福的人。喂马、劈柴，周游世界。从明天起，关心粮食和蔬菜。我有一所房子，面朝大海，春暖花开')
w.to_file('output2.png')
```
