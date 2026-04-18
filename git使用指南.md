# git使用指南



## 一、Git仓库创建（队长）

### 1.去github官网上创建一个仓库（private）

eg:git@github.com:GoFarforDream/voyager-aiedu-system.git 就是我创建的仓库

## 二、仓库初始化（队长）

### 1.进入到项目

初始化本地仓库

```bash
git init
```

### 2.给文件追加监控

```bash
git add .
```

### 3.提交到本地仓库

```bash
git commit -m "提交内容"
```

### 4 .链接远程仓库

```bash
git remote add origin git@github.com:GoFarforDream/voyager-aiedu-system.git
```

### 5.首次推送远程

```bash
git push -u origin master
```

之后的推送

```bash
git push
```

## 三、仓库合作者邀请

去github的仓库里邀请合作成员，等待成员完成认证

## 四、合作者克隆仓库

### 1.初始化配置和创建ssh公钥
```bash
git config --global user.name "你的名字"

git config --global user.email "你的邮箱"

git config --list

ssh-keygen -t ed25519 -C "你的邮箱"
```

### 2.在github的setting中的ssh的选项配置公钥

### 3.仓库克隆

```bash
git clone git@github.com:GoFarforDream/voyager-aiedu-system.git
```

## 五、从develop创建分支并迁出

### 1.查看git分支

```bash
git branch
```

### 2.如果没有develop分支的话，创建develop分支

```bash
git branch develop

git checkout develop
```

### 3.关联远程分支

```bash
git branch --set-upstream-to=origin/develop develop
```

### 4.拉取develop分支（每次合并提交前，都要干的事情）

如果自己已经写了些东西，怕被冲走的话，就先暂存一下

```bash
git stash
```

然后再拉取

```bash
git pull
```

### 5.创建自己的分支

```bash
git branch gfr

git checkout gfr
```
同步完成后，再恢复之前的代码

```bash
git stash pop
```
## 六、写代码，完成后合并提交代码

当你写完代码后

### 1.追加监控文件

```bash
git add .
```

### 2.查看状态

```bash
git status
```



### 3.本地提交

```bash
git commit -m "你做了什么"
```

### 4.查看当前分支并迁出到develop分支

#### （1）查看分支

```bash
git branch 
```

#### （2）切换到develop

```bash
git branch develop
```

#### （3）确认是develop

```bash
git branch
```

### 5.合并自己的分支到develop

将自己的分支合并到develop分支

```bash
git merge gfr
```

如果有冲突，需要自己处理冲突

### 6.推送develop分支到远程

```bash
git push 
```

接下来就是等小组负责人审核代码，确认合并
