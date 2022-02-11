# GitNotes
## 基础操作
0. git init:初始化一个版本库
1. git add fN:将文件提交到临时存储区
2. git commit -m "日志信息" FN  :将文件提交到本地库。
3. git config --global user.name 用户名：设置用户签名
4. git config --global user.email 邮箱: 设置用户邮箱
5. git reflog:查看历史记录      git log:查看版本详细信息
6. git reset --hard 版本号：版本穿梭
7. git init:初始化本地库
8. git status:查看本地库状态
9. rm fN: 删除的是暂存区中的文件，若删除后，需重新提交到暂存区中。
10. git branch 分支名：创建分支
11. git branch -v:查看分支
11_1. git branch -d 分支名：删除某个分支
12. git checkout 分支名：切换分支
13. git merge 分支名:把指定的分支合并到当前分支上
14. 不同分支，同一文件修改差异：如果再同一个部位修改数据。=使用git merge 分支名。新数据会直接进行覆盖旧数据。如果是不同部位进行修改，系统无法判断哪一个数据才是真的必须人为进行修改数据之后再提交到缓存区，再提交到本地库（本地库不能带文件名，不然有歧义识别不出来哪一个），使用命令git commit -m "merge ss" （不用文件名）。
15. git remote -v：查看当前所有远程地址别名
16. git remote add 别名 远程地址：起别名
17. git push 别名 分支：推送本地分支上的内容到远程仓库
18. git clone 远程地址：将远程仓库的内容克隆到本地
19. git pull 远程库地址别名 远程分支名:将远程仓库对于分支最新内容拉下来后与当前本地分支直接合并
20. git add -A . : 提交该文件夹中的所有文件
21. git commit -m "提交注释":提交所有注释到本地库
22. git reset --hard HEAD^:回退到当前版本的前一个版本。HEAD^^表示前两个版本。也可以用HEAD~1：表示当前版本的前一个版本。
23. git reset --hard 版本号：回退到某个固定版本。
24. git checkout -- fileName:当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改
25. git diff HEAD -- code.txt:将工作区中的code.txt与HEAD 版本中的code.txt进行比较。
26. git rm hello.txt:永久删除，无法撤销   并且git commit -m "删除文件"
27. git stash:将当前工作现场隐藏起来
28. git stash pop:从缓冲中释放出来
29. 创建公钥：ssh-keygen -t rsa -C "*@*.com"
30. 修改默认分支名称：git branch -m main master  或是修改.gitconfig
31. 检出仓库：$ git clone git://github.com/jquery/jquery.git
32. 查看远程仓库：$ git remote -v
33. 添加远程仓库：$ git remote add [name] [url]
34. 删除远程仓库：$ git remote rm [name]
35. 修改远程仓库：$ git remote set-url --push[name][newUrl]
36. 拉取远程仓库：$ git pull [remoteName] [localBranchName]
37. 推送远程仓库：$ git push [remoteName] [localBranchName]
38. 查看本地分支：$ git branch
39. 查看远程分支：$ git branch -r
40. 创建本地分支：$ git branch [name] ----注意新分支创建后不会自动切换为当前分支
41. 切换分支：$ git checkout [name]
42. 创建新分支并立即切换到新分支：$ git checkout -b [name]
43. 删除分支：$ git branch -d [name] ---- -d选项只能删除已经参与了合并的44. 分支，对于未有合并的分支是无法删除的。如果想强制删除一个分支，可以使用-D选项
45. 合并分支：$ git merge [name] ----将名称为[name]的分支与当前分支合并
46. 创建远程分支(本地分支push到远程)：$ git push origin [name]
47. 删除远程分支：$ git push origin :heads/[name]
48. 查看用户名：git config user.name
49. 查看邮箱:git config user.email



## 遇到的问题
问题：
1. Git提交数据失败 error: failed to push some refs to 'https://github.com/XXXXXXX/gif.git'

解决：我这边的原因是：当初在github上申请远程库的时候，多创建了一个README.md文件，导致这个文件和本地 的文件不匹配。

2. 解决Git中fatal: refusing to merge unrelated histories
解决：这是由于这个git 本地库的commit历史与远处的github的历史是不一致的。导致出现这样的情况。

3. 若更改(删除)了本地文件夹中的某个文件，提交的时候，就直接git add --all。将所有都提交，然后push上去。

## 参考
1. [Git从入门到精通（全）](https://blog.csdn.net/weixin_47872288/article/details/120812667)
2. [git使用教程](https://pypypy.blog.csdn.net/article/details/104551896)
3. [git提交本地分支到远程分支](https://www.cnblogs.com/springbarley/archive/2012/11/03/2752984.html)
