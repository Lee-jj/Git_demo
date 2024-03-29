# Git_demo
常用的git命令

``` shell
//设置用户签名
git config --global user.name xxx
git config --global user.email xxx@xxx.com

git init 		                    // 初始化本地库
git status 		                    // 查看本地库状态
git add 文件名    	                // 添加到暂存区
git commit -m "日志信息" 文件名	     // 提交到本地库
git reflog		                    // 查看版本信息
git log		                        // 查看详细版本信息
git reset --hard 版本号	            // 版本穿梭

git branch 分支名	                // 创建分支
git branch -v 	                    // 查看现有分支
git checkout 分支名	                // 切换分支
git merge 分支名	                // 把分支名所示分支合并到本分支
//创建新分支后，master不修改，此时merge不会产生冲突
//创建新分支后，若master进行了修改，此时merge会需要人为修改冲突的代码后，运行git add 文件名 和git commit -m "日志信息"(注意此时不加文件名)进行提交
//解决Git中fatal: refusing to merge unrelated histories[https://developer.aliyun.com/article/614459]

//上传至github远程仓库
//仓库名最好与本地库(文件夹)名称一致
git remote -v	                    // 查看当前所有远程地址别名
git remote add 别名 远程地址	    // 给远程地址起别名
git remote rm 别名                  // 删除别名
git push 别名 分支名(master) 	    // 推送本地分支上的内容到远程库
git pull 别名 分支名(master)        // 拉取远程库分支到本地库
git clone 远程地址		            // 克隆远程库到本地
// git提交或克隆报错fatal: unable to access ‘https://github.com/tata20191003/autowrite.git/‘: Failed to connec
// 上述问题解决方案：https://blog.csdn.net/good_good_xiu/article/details/118567249

// 对某个文件取消跟踪 
git rm --cached readme1.txt         // 删除readme1.txt的跟踪，并保留在本地。
git rm --f readme1.txt              // 删除readme1.txt的跟踪，并且删除本地文件。

//设置SSH免密登录
git-keygen -t rsa -C 邮箱签名        // 在C:\Users\user路径下运行git bash生成.ssh文件夹，再将id_rsa.pub中的内容添加到自己github账号下，获得SSH链接
git pull SSH链接 分支名(master)      // 拉取

// 克隆远程仓库流程
1. 本地文件夹中使用 git clone 命令直接克隆远程仓库的ssh（本地已经有密钥）
2. 遇到问题：ssh: connect to host github.com port 22: Connection timed out，解决：参考：https://zhuanlan.zhihu.com/p/521340971，修改22端口为443

```
