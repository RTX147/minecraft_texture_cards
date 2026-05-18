# 我的世界材质包卡片
# [中文](./README.zh-CN.md)/[English](./README.en-US.md)
你还在用这种看起来老式的文本描述吗？  
![演示图片](Mockup/01.png)  
不妨来试试这种卡片式的,你既可以让它变成风景，也可以让它变成一张名片  
![演示图片](Mockup/03.png)  
![演示图片](Mockup/02.png)  

# 临时注意事项
###### 由于教程还未编辑完成所以临时写出注意事项,以下的注意事项都是临时的,随时可能面临改动
### 1
如果你发现你的卡片变成了这样  
![演示图片](Mockup/04.png)  
那么请不要慌张,这是正常现象这是因为处于未装载状态,需要装载后才会正常显示卡片  
###### 如果你有什么方法可以在不装载时显示卡片欢迎提交PR,或者邮件联系我
### 2
在[材质包信息文件](Repository/Resource_Pack/pack.mcmeta)  
```json
{
  "pack":{
    "pack_format":15,
    "supported_formats":[1, 147],
    "description":"§bminecraft texture cards\n§f\ue146\ue147\ue148"
  }
}
#RTX147
```
中
```md
`\n§f\ue146\ue147\ue148`
```
是不可改动的,如果改动会出现显示错误,(但5.会提到之中需要改动的位置)
其他的请随意,包括这一段  
```md
`§bminecraft texture cards`
```  
可以改成你想显示的介绍话语
### 3
请确保你的介绍话语绝对没有像这样,超过第一行，来到第二行   
![演示图片](Mockup/05.png)  
否则会出现错误  
像这样↓的择可以,即使是写满第一行,也没有问题  
![演示图片](Mockup/06.png)  
即使是写未满第一行，已经有`\n`自动换行了再不需要打换行符
### 4
在[字符替换文件](Repository/Resource_Pack/assets/minecraft/font/default.json)  
```json
{
 "providers":
  [
   {
   "type":"bitmap",
   "file":"minecraft:147/146.png",
   "ascent":29,
   "height":32,
   "chars": ["\ue146"]},
   {
   "type":"bitmap",
   "file":"minecraft:147/148.png",
   "ascent":29,
   "height":32,
   "chars": ["\ue148"]},
   {
   "type": "space",
   "advances":{"\ue147": -1.19}
   }
  ]
}
```
中的  
```md
`\ue146`和`\ue148`
```
将项目应用到你的材质上是必须改动的,但改动必须遵守以下规则,否则会出现错误,甚至无法装载  
1.不得继续使用`\ue146`和`\ue148`  
2.改名只能改动`\ue`之后的数字部分,最高三位数不得超过,也不能小于三位数  
3.如果你有其他材质,请不要与其他材质上的名一样,否则同时装载时会出现错误   
4.在`\ue`之后填写可以包含以下内容,其余则不行  
###### 0-1  a-f  A-F
###### 字母加数字`\uea6f`纯数字`\ue198`纯字母(可以纯大写或纯小写)`\ueabc`大写加小写`\ueAbC`都是可以的
5.`\ue146`和`\ue148`改动后不可相同如`\ue146`和`\ue148`改为`\ue777`和`\ue777`不行  
6.改动后需要一同改动[材质包信息文件](Repository/Resource_Pack/pack.mcmeta)  
中的`\ue146`和`\ue148`但不一样的是你在[字符替换文件](Repository/Resource_Pack/assets/minecraft/font/default.json)中改的叫什么这里的就应该同步叫什么  
7.[卡片图片1](Repository/Resource_Pack/assets/minecraft/textures/147/146.png)的像素是-长边256-短边72  
[卡片图片2](Repository/Resource_Pack/assets/minecraft/textures/147/148.png)的像素是-长边95-短边72  
8.像素多了少了都会影响图片显示  
9.他们合起来是一张351比72的图片，可以根据这个来制作你的卡片 

#### 很抱歉项目才刚开始还没有完善-_-ll
###### (可以先问候作者让他先教你😋)
