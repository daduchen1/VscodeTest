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
#### 1、生成ssh密钥并关联GitHub  
生成ssh的命令`ssh-keygen -t ed25519 -C "your_email@example.com"`,生成后一般存在.ssh文件夹，其中`id_ed25519`是私钥，`id_ed25519.pub`是公钥，使用`cat`命令可以查看公钥内容并给到github，也可以`pbcopy < ~/.ssh/id_ed25519.pub  # 自动复制到剪贴板`  
#### 2、在GitHub创建空仓库  
#### 3、在终端打开目标文件夹  
#### 4、`git init`  
##执行`git init`后，默认生成一个分支，叫master分支，于是会用到后面的 git branch -M main命令，现代git中一般初始化仓库地都是生成main分支  
#### 5、`git add`  
    ##`git add .`表示添加全部文件，`git add 文件名.格式`表示上传某个文件，上传文件夹是`git 文件夹名`  
#### 6、`git commit -m "操作了什么"`  
#### 7、`git branch -M main`  
  ##`-M`表示强制把分支重命名成`main`   
#### 8、`git remote add origin ssh地址`  
  ##将远程仓库的 `SSH` 地址以别名 `origin` 添加到本地仓库的远程仓库列表中。  
  ##其中`add`表示添加一个新的远程仓库链接，`origin`是一个约定俗成的仓库的别名，它用来代替ssh地址(比如git@github.com:username/repo.git)或url地址  
##### 8.1 关于`origin`的一些点  
a、关联远程仓库（初始化）  
第一次将`本地仓库`与`远程仓库`连接时，通过以下命令`添加仓库别名`  
`git remote add origin git@github.com:username\repo.git`  
b、推送代码到远程仓库  
首次`推送`本地分支到远程仓库时，必须指定目标远程仓库别名（即 origin）：  
  `git push -u origin main`  
  将本地的 main 分支推送到名为 origin 的远程仓库，并建立跟踪关系（-u 参数）。
后续推送只需简写 ：  
建立跟踪关系后，后续只需运行 `git push` 即可自动对应到 `origin/main`，无需重复指定。  
c、克隆仓库时的默认别名  
当你用 `git clone` 克隆远程仓库时，`Git` 会自动将远程仓库命名为 `origin`：  
`git clone git@github.com:username/repo.git`  
效果 ：  
本地会生成一个名为 `origin` 的远程仓库别名，指向原始仓库地址。  
#### 9、`git push -u origin main`   
`git push -u main`vs`git push main`  
区别 ：  
`git push -u main` 中的 `-u`（或 `--set``-upstream`）会 建立本地分支与远程分支的跟踪关系  
`git push main` 只是单纯推送代码到远程的 `main` 分支（前提是远程已有该分支或权限新建分支）  
为什么需要 `-u`？  
第一次推送时，本地分支需要绑定到远程分支。使用 `-u` 后，`Git` 会记住这种关联关系，后续只需运行 `git push` 或 `git pull` 即可自动对应到远程分支。  
如果不加 `-u`，每次推送都需要手动指定远程分支（如 `git push origin main`）    
例如  
#首次推送并绑定跟踪关系  
`git push -u origin main`  
#后续只需直接推送（无需重复指定分支）  
`git push `     

### 举例：  
```  
# 初始化仓库并切换到 main 分支
git init
git branch -M main

# 关联远程仓库
git remote add origin git@github.com:yourname/yourrepo.git

# 首次推送并绑定跟踪关系
git push -u origin main

# 后续只需直接推送
git push  
```
明天要做的  
~~1、熟悉分支使用~~  
1、从GitHub通过git把仓库下载到本地的使用方法包括增删改查  
2、vscode操作实现git操作
