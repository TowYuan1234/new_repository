#Linux高级编程

##Github 
  
  关键字查询<br>
  * awesome 去此标签类别中查询项目
  * python tutorial 查询资料，书籍，文档
  * socket sample 查询对应技术的代码样本

##github 三要素

  * Repository仓库
    * 仓库是github项目管理存储基本单位
    * 一个仓库中存储一个项目，一个用户可以拥有多个仓库，一般仓库粉味public，private

  * Commit 提交
    * 程序员在整个开发周期，由大量的对代码资源的迭代和修改，都可以通过commit的方式进行记录，便于程序员回溯代码，即使这些代码被删除
    * 提交便于使用者观察整个工程的开发流程以及设计流程

  * Branch 分支
    * 在仓库中可以包含多个分支，分支才是代码文件的第一存储单位，默认的仓库主分支为master/main
    * 可以管理代码存储，便于多人协作开发

![图片理解](D:\colin\0912\linux高阶\1.png "点击预览")
  
##仓库内容
  * code 资源存储，代码资源，二进制，项目管理脚本，许可证等
  * issues 使用时遇到的bug或进行提交，等待反馈
  * README 使用markdown语言编写，工程自述文件，开发进度，版本更新，使用介绍等等
  * LICENSE 许可证
    * GPL 2.0,3.0 Apahce 2.0,Mit 这些许可证，给使用者最大的使用权限以及最少的限制

## Git软件，分布式版本控制系统

  * 仓库管理软件，使用git管理私人代码或企业代码

## 设备认证方法
  
  1. 如何让网站的账户与设备绑定，后续完成代码的管理，上传下载
    1. git init //创建本地仓库
    2. git config --list //查看git的配置文件
    3. git config --global user.email "邮箱" //绑定邮箱
    4. git config --global user.name "用户名" //绑定用户名
    5. ssh-keygen -t rsa -C "注册用的邮箱" //创建本地密文
    6. 去对应的目录查找密文文件
    * rsa.pub复制密文，粘贴 settings->\ SSH key and GPG -> new ssh key ->粘贴
    * ssh -T git@github.com //测试关联是否成功
  2. 为目标仓库起别名，定位目标仓库，后续上传
    1. git remote add origin "ssh地址" //为ssh仓库地址创建别名为origin
    2. git remote remove origin  //删除origin别名
    3. git remote add origin "ssh地址" //为ssh仓库地址创建别名为origin

##本地设备与云端仓库的交互逻辑

![图片理解](D:\colin\0912\linux高阶\2.png "点击预览")
   * git add //添加内容
   * git rm //删除本地文件并删除仓库数据
   * git restroe //恢复被删除（仓库存在）

## 代码更新的依赖关系被破坏
   1. 本地内容要比云端新，完成更新替换，但是如果直接修改云端内容，导致，本地内容无法再次提交
   2. 解决方法：先拉取git pull 云端内容，与本地内容合并或操作，而后再次提交即可
    * git pull --rebase origin master
    * git rebase --skip "忽略本地内容，保留云端内容"
    * git rebase --about "忽略本地内容，保留云端内容"
    * git rebase --cintinue "忽略本地内容，保留云端内容"

##下载开源代码
   * git clone "https仓库地址" //下载开源项目code资源
 
##分支Branch
  * 关于分支的相关命令，创建分支，选择分支，合并分支等等

##Markdown语言
  * GitHub 可以编写readme，文本修饰语言







