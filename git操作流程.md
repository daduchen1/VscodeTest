# GIT访问GitHub操作流程及常见命令

## 一、git工作流程图
![示例图片](images/GIT_pic.png)
注：插入图片的代码是  
`![故障时显示的内容](图片的相对路径)`  
调整图片尺寸的代码是  
`<img src="images/GIT_pic.png" width="700" />`  
调整图片位置的代码是  
```
<p align="center">
  <img src="images/GIT_pic.png" width="700" />
</p>
```  
换行需要在行尾添加两个空格
## 二、本地文件上传到GitHub
### 流程：
1、生成ssh密钥并关联GitHub  
2、在GitHub创建空仓库  
3、在终端打开目标文件夹  
4、`git init`  
5、`git add` 
    `git add .`表示添加全部文件，`git add 文件名.格式`表示上传某个文件，上传文件夹是`git 文件夹名`  
6、`git commit -m "操作了什么"`  
7、`git branch -M main`  
8、`git remote add origin ssh地址`  
9、`git push -u origin main`   
  
    
明天要做的  
1、熟悉分支使用  
2、从GitHub通过git把仓库下载到本地的使用方法包括增删改查