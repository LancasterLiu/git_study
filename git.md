# git



## 版本控制

> 分类

1. **本地版本控制**

适合个人



2. **集中版本控制**

版本数据放在**服务器**上。

==缺点==：

（1）存在服务器损坏风险

（2）无分支



3. **分布式版本控制**

（1）同步到每个用户本地

（2）可离线提交



## 安装配置+基础知识学习（Linux基础命令）

![image-20220214222823349](C:\Users\Lancaster\AppData\Roaming\Typora\typora-user-images\image-20220214222823349.png)

> linux基本指令

![image-20220215224441948](C:\Users\Lancaster\AppData\Roaming\Typora\typora-user-images\image-20220215224441948.png)

==切勿在Linux上尝试==

```==
rm -rf / 
会格式化电脑
```



> 配置

配置环境变量只是为了可以随时使用，但已存在于右键，无需配置，且已自动配置

1. 查看

- 查看配置：**git config -l**
- 查看系统配置:**git config --system --list**
- 查看本地配置:**git config --global --list**

2. 配置(本质读写文件)

- git config --global user.name "Lancaster"
- git config --global user.email LancasterLiu_cryp@163.com



## 基本理论

> 工作区域

1. 工作目录
2. 暂存区
3. 资源库
4. git远程仓库

![image-20220228183559428](C:\Users\Lancaster\AppData\Roaming\Typora\typora-user-images\image-20220228183559428.png)

- 工作区：本地存放项目文件代码
- 暂存区：临时存放改动，其实为一个列表信息文件
- 本地仓库：存放文件变化数据
- 远程仓库：git



## 搭建本地项目实践

1. 在本地搭建一个仓库

```
#初始化
git init
```

```
#克隆远程仓库
git clone [url] 
#url:https://github.com/LancasterLiu/spider
```



## 文件操作

> 文件4种状态：

> 1. Untracked（未跟踪）：即在文件夹中，但不在git库中。可通过==git add .==使状态变为**Staged**
> 2. Unmodify（文件已入库但未修改）：可通过==git rm==使状态变为**Untracked**即移除；或修改文件使状态变为**Modified**
> 3. Modified（已修改）：可通过==git add .==使状态变为**Staged**；或可通过==git checkout==使状态变为**Unmodify**，即还原原来文件
> 4. Staged（暂存）：可通过==git commit==使修改同步到git库，状态变为**Unmodify**；或通过==git reset HEAD filename==取消暂存，状态变为**Modify**



> 查看状态

```
#查看所有文件状态
git status
```

```
#查看指定文件状态
git status "filename"
```

```
#添加所有文件到暂存区
git add .
```

``` 
#提交暂存区文件到git仓库
git commit -m “文件描述”
```



> 上传时忽略文件

在主目录下创建.gitignore文件，可以控制不上传哪些文件

- 使用手册
    - #为注释
    - 可使用linux通配符
    - ！代表例外规则，不被忽略
    - /路径分隔符
- 举例

```
#注释
*.txt		#忽略所有txt文件
!lib.txt 	#lib.txt除外
/temp		#不忽略temp
main/		#忽略main下所有文件
main/*.txt	#忽略main下所有txt文件
```



## 配置SSH公钥

1. 生成公钥文件

```
#直接在bash里面输入
ssh-keygen -t rsa
```

2. 复制.pub文件信息至gitee

3. 创建git远程仓库



## 分支

- 查询

```
#本地分支
git branch
#远程分支
git branch -r
```

- 创建

```
#仍停留在原分支
git branch 分支名
#切换到新分支
git checkout -b 分支名
```

- 合并

```
#合并指定分支到当前分支
git merge 分支名
```

- 删除

``` 
#本地
git branch -d 分支名
#远程
git branch -dr 分支名
git push origin --delete 分支名
```

- 切换

```
git checkout 分支名
```

