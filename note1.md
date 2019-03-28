#水平居中
##行内元素
水平居中是通过给父元素设置 text-align:center 来实现的。
##块状元素
- 定宽高  
设置“左右margin”值为“auto”来实现居中的
- 不定宽高  
**1.**加入table标签。利用table标签的长度自适应性（table其长度根据其内文本长度决定），因此可以看做一个定宽度块元素，然后再利用定宽度块状居中的margin的方法。  
**2.**设置display：inline。显示类型设为行内元素，进行不定宽元素的属性设置。用text-align：center。  
**3.**设置 position:relative 和 left:50%：利用 相对定位的方式，将元素向左偏移50%,即达到居中的目的.  
父元素设置float；position：relative和left50%，子元素设置position：relative和left-50%。  
# 垂直居中
## 父元素高度确定的单行文本
通过设置父元素的height和line-height（** 弊端**当文字的长度大于块的宽度就会有内容脱离了块）
## 父元素高度确定多行文字/图片等
### 1使用插入table
使用插入table（包括tbody td tr）并设置vertical-align：middle（在父元素设置vertical-align对于inline-block类型的子元素都有用)。  
###2设置块级元素的 display 为 table-cell（设置为表格单元显示），用vertical-align 属性。  
#隐形改变display类型  
设置position：absolute或者float，元素的display显示类型就会自动变为以 display:inline-block。  
#GitHub
- 创建版本库 
$ mkdir 文件名
$ cd 文件名
$ pwd
- 通过git init把这个目录变成Git可以管理的仓库
- git add把文件添加到仓库（git add 文件名）
- git commit把文件提交到仓库（git commit -m"说明注释"）
- git status掌握仓库当前的状态
- git diff查看具体修改了什么。（git diff 文件名）
- git log可以查看从近到远提交的版本。
-  git reset --hard HEAD^回到上一个版本（HEAD~n：回到第前n个版本）
-   git reflog查看命令历史
-   git reset --hard 版本号。回到版本号对应的版本。
-   cat 文件名，查看文件内容 
- 工作区与版本区  
git add把文件添加进去，实际上就是把文件修改添加到暂存区；
git commit提交更改，实际上就是把暂存区的所有内容提交到当前分支。
- 撤销  
git checkout -- 文件名，把文件在工作区的修改全部撤销，有两种情况：  
一种是readme.txt自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；  
一种是readme.txt已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。  
已经提交了不合适的修改到版本库时，想要撤销本次提交，可以版本退前一个，前提是没有推送到远程。
- 删除  
直接在文件管理器中把没用的文件删了，或者用rm命令  
rm命令：$ rm 文件名  然后$ git rm 文件名 删掉，并且git commit  
删错：$ git checkout -- 文件名，可以恢复。
###先创建本地，再推送到远程
- 同步：关联：$ git remote add origin git@github.com:用户名/文件名。$ git push -u origin master：推送到远程。
###先在远程创建仓库
1. 登录GitHub，创建一个新的仓库。
2. 克隆  git clone git@github.com:用户名/文件名
#markdown
链接 :[]()  
加粗 :**  **  
斜体字: * *  
高亮:== ==  
段落 : 段落之间空一行  
换行符 : 一行结束时输入两个空格  
列表 :*  
引用 :>  
内嵌代码 : ``  
画水平线 (HR)  
方框:- [ ] -  
#transform transition  
1. transform-origin 改变被转换元素的位置。(x-axis y-axis z-axis;)
2. transition-property ：规定设置过渡效果的css属性名称:none all.  
3. transition-duration：time.完成过渡效果的时间。
4. transition-timing-funcyion：指定过渡函数，规定速度效果的速度曲线。  
ease速度由快到慢，逐渐变慢  
linear 恒速  
ease-in呈加速状态
ease-out呈减速状态
ease-in-out先加速再减速
5. transform: rotate(ndeg);顺时针旋转n°
6. scale对文字或图像缩放处理 
transform: scale(0.5);水平方向、垂直方向缩小一半  
transform: scale(0.5, 2)：水平方向缩小一半、垂直方向放大一倍
7. skew文字或图像倾斜处理
transform: skew(30deg, 30deg);水平方向、垂直方向倾斜30°
transform: skew(30deg)；只在水平方向倾斜30°
8. translate文字或图像的移动处理，在参数中分布指定水平方向上的移动距离与垂直方向上的移动距离。  
transform: translate(50px, 50px);水平方向、垂直方向移动50px
transform: translate(50px);只在水平方向移动50px  
（Internet Explorer 10、Firefox、Opera 支持 transform-origin 属性。  
Internet Explorer 9 支持替代的 -ms-transform-origin 属性（仅适用于 2D 转换）。  
Safari 和 Chrome 支持替代的 -webkit-transform-origin 属性（3D 和 2D 转换）。  
Opera 只支持 2D 转换。)  