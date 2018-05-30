# git-configure
## 初始化：
* ssh-keygen 时，请先进入到 ~/.ssh 目录，不存在的话，请先创建。并且保证 ~/.ssh 以及所有父目录的权限不能大于 711

ssh-keygen -f test   -C "test key"  //-f 选项指定生成文件的文件名  -C选项是公钥文件中的备注
                ~~文件名   ~~~~ 备注  

* $ ssh-keygen -t rsa -C "youremail@yourcompany.com” -f ~/.ssh/id-rsa
* 密钥类型可以用 -t (rsa dsa)选项指定。如果没有指定则默认生成用于SSH-2的RSA密钥

## 语法
ssh-keygen(选项)
### 选项
* -b：指定密钥长度；
* -e：读取openssh的私钥或者公钥文件；
* -C：添加注释；
* -f：指定用来保存密钥的文件名；
* -i：读取未加密的ssh-v2兼容的私钥/公钥文件，然后在标准输出设备上显示openssh兼容的私钥/公钥；
* -l：显示公钥文件的指纹数据；
* -N：提供一个新密语；
* -P：提供（旧）密语；
* -q：静默模式；
* -t：指定要创建的密钥类型。


* git push --set-upstream origin 分支名称
* 
* 长期存储密码：  http免密码更新代码
* git config --global credential.helper store
* git merger 分支名称   合并分支
* git branch -d 分支名  删除分支
* git push origin —delete 分支名称  删除远程分支
* git branch -dr  远程分支名称         删除远程分支
* git pull  拉取下来
* git add 文件名或者 —all
* git commit 到 本地仓库
* git push orign master(本地分支):developer更新到服务器
* git branch --set-upstream-to=origin/develop develop  跟服务器关联 （pull使用）
* git config --global push.default simple（push使用）
* git . ignore 编辑git上传规则，屏蔽一些多余的文件
* git log 查看日志信息
* git branch -r 查看远程分支然后pull 更新
* git -rm 删除文件
* vim .gitignore git添加过滤规范
* git reset —hard 454rh44 (SHA)回滚版本，删除的版本也可以搞定
* 
* git checkout - 切换到下一个分支
* 
* git branch -a  查看所有分支包含线上


### ssh-keygen设置ssh无密码登录

* ssh-keygen - 生成、管理和转换认证密钥，包括 RSA 和 DSA 两种密钥
密钥类型可以用 -t 选项指定。如果没有指定则默认生成用于SSH-2的RSA密钥
 
## 配置：
* 1、在本地机器中的~/.ssh/目录下执行下命令
ssh-keygen -t dsa
将生成两个文件,id_dsa和id_dsa.pub
 
* 2、将id_dsa.pub拷贝到远程机器,并且将id_dsa.pub的内容添加到~/.ssh/authorized_keys中
cat id_dsa.pub >>authorized_keys
注意:目录.ssh和文件authorized_keys的权限必须是600
 
完成以上操作之后，用户从本地机器到远程机器就不需要用密码了
