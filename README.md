# myweather

gitbash：是一个继承git命令的命令工具，有些命令类似linux命令

## 常用基本命令

  绝对路径
  cd /路径

  相对路径
  cd ./路径
  cd 路径

  查看文件夹、文件
  ls

  创建文件
  touch 文件路径1 文件路径2 文件路径3 ...

  创建文件夹
  mkdir 文件夹路径1 文件夹路径2 ....

  移动文件
  mv 旧文件路径 新文件路径

  修改文件名称
  mv 旧文件名称 新文件名称

  返回上一级文件夹
  cd ..

  删除文件
  rm 文件路径

  删除文件夹 -r: 递归, -f: 强制
  rm -rf 文件夹路径

  查看文件内容
  cat 文件路径

  编辑文件
  vim 文件路径

  1、按下键盘i键，进入编辑模式
  2、通过键盘方向键移动光标进行编辑
  3、按下键盘esc退出编辑模式
  4、输入:wq，保存退出  或者 输入q!，退出不保存


清除命令历史记录
  clear


git: 一个分布式版本控制系统
CCkk00123kang

粘贴

手提
shift + fn + insert

台式
shift + insert

配置github用户信息（只需配置一次）
git config --global user.name '你的github用户名'
git config --global user.email '你的github注册邮箱'

克隆项目代码
git clone 远程仓库地址

查看github仓库文件变化状态
git status


将文件推送到远程仓库的四个步骤
  git add .
  git commit -m '你的注释'
  git pull
  git push -u origin 分支名



配置ssh
  生成ssh key
  ssh-keygen -t rsa -C "你的github注册邮箱"

  id_rsa: 私钥
  id_rsa.pub： 公钥，需要配置到github


  .gitignore文件：忽略指定文件不要添加到暂存区

  查看分支
  git branch

  切换分支
  git checkout 分支名称

  合并分支
  git merge 被合并的分支

  删除远程分支
  git push origin :删除的分支名

  删除本地分支
  git branch -d 删除的分支名

```txt
测试代码冲突
尚文玉

用户名：cckk00
邮箱：cckk00@126.com
密码：CCkk00123kang

1-先配置我的信息
git config --global user.name 'cckk00'
git config --global user.email 'cckk00@126.com'

2-先在凭证管理器删除github凭证

403

3-拉取远程仓库
git clone https://github.com/cckk00/myweather.git

4-约定修改index.js
git add .
git commit -m '你的注释'
git pull
git push -u origin master


如果执行 git pull，产生冲突时的表现
From github.com:cckk00/myweather
   821564d..3ab0fdc  master     -> origin/master
Auto-merging index.js
CONFLICT (content): Merge conflict in index.js
Automatic merge failed; fix conflicts and then commit the result.

代码冲突表现

<<<<<<< HEAD
  var animal = ['白兔', '蜻蜓'];

  animal.forEach(v => {
    console.log('v ==> ', v);
  })
=======
  console.log('loaded');
  console.log('hello');
  function fn() {
    var a = 1;
    return a;
  }
  function fn2(){
	  var b = 2;
	  return b;
  }
>>>>>>> 3ab0fdcca8845dc398989c3f4970bafef7e85c54
```


git pull
 network

```txt
git状态撤销
  1-修改、删除、新增文件，但没有执行 git add
    撤销命令：git reset --hard

  2-修改、删除、新增文件， 执行 git add，没有执行 git commit
    撤销命令: 
      将文件撤出暂存区：git reset
      将文件内容恢复上一次的内容：git reset --hard

  3-修改、删除、新增文件，执行 git add，执行 git commit，没有执行git push
    撤销命令：git reset --hard origin/分支名

  4-修改、删除、新增文件，执行 git add，执行 git commit，执行git push
    撤销命令：
      将本地仓库恢复上一个版本：git reset --hard HEAD^
      强制更新远程仓库：git push -f
```txt