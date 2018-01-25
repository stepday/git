# 有什么料？
这里主要收集整理一些git文件管理器的一些日常操作指令

<b>为了解决多人协同开发项目全部在master分支上操作，实现不了局部更新服务器的问题</b>，我们需要进行分支管理、开发、提交合并主分支的操作，这样合并主分支的时候可以保障主分支的东西随时都是可以更新到正式环境，不会引起前后端更新不同步的问题。

## 一、一般项目成员的git日常操作

#### 1、新建一个新的分支 一般根据自己的姓名简拼进行创建，比如下面的分支
<pre>
git branch origin-stepday
</pre>

#### 2、切换到某个分支
如果不知道应该切换到某个分支，或者想看下目前分支有哪些，可以用下面的指令查看:
<pre>
git branch
</pre>
切换到某个分支用下列指令:
<pre>
git branch origin-stepday
</pre>

#### 3、修改分支代码后按照日常操作提交修改
<pre>
git add .
git commit -m '提交分支修改'
git push origin origin-stepday //提交到分支版本
</pre>

#### 4、删除分支
<pre>
git branch -d origin-stepday(一般我们不需要删除分支 一直保持既可以)
</pre>

## 二、主分支管理员的日常操作
<pre>
1、根据每个分支的合并请求情况查看其分支与主分支的差异地方在哪里并进行代码Review；

2、没问题就开始次分支合并到主分支上
git checkout master //切换到主分支
git merge origin-stepday //合并次分支至主分支
git add .
git commit -m '提交次分支origin-stepday的修改至主分支内容'
git push //推送至主分支服务器
</pre>

## 三、其他日常git操作指令
可以暴力的采用git help 查看所有的git指令描述，也可以直接访问这个地址：<a href="http://www.runoob.com/git/git-tutorial.html" target="_blank">http://www.runoob.com/git/git-tutorial.html</a>
<pre>
git log //查看
git reset --hard 对应版本的id串  //回退到某个版本
git push -f -u origin master //将修改推送到主分支
</pre>