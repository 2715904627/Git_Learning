
配置：
	name
		git config --global user.name "Kadupul"
	email
				git config --global user.email "2715904627@qq.com"
使用：
	git status
		- 查看当前仓库状态
	git init
		- 初始化仓库
	刚刚添加到项目中的文件处于未追踪状态
		未跟踪--->暂存
			git add FILENAME
			git add *
		暂存--->未修改
			git commit -m LOG
			（git commit -a -m LOG 提交所有已修改文件  未跟踪的文件不会提交）
		未修改--->已修改
			修改仓库文件代码即可
	常用命令：
		回到上次提交位置
			git restore FILENAME（只能恢复未处在暂存区的文件)
			git restore *
			git restore --staged FILENAME 取消暂存状态
		删除文件
			git rm FILENAME(只能修改未修改数据)
			git rm -f FILENAME 强制执行
		移动文件
			git mv from  to 
	分支：
		查看分支(标记目前分支)
			git branch
		创建新分支
			git branch BRANCHNAME
		删除分支
			git branch -d BRANCHNAME	
		切换分支
			git switch BRANCHNAME
			git switch -c BRANCHNAME(创建并切换分支) 
		合并分支
			一、通过merge合并
				切换回主分支;
				git merge BRANCHNAME;
				{两种方式：
				1.fast forward 
				2.Auto Merge （需要自己确定冲突文件修改方式：current/incoming/both）
				}
				git branch -d BRANCHNAME
			二、通过变基合并（rebase）
				1.发起变基时，git会寻找两条分支的最近的共同祖先
				2.对比当前分支相对于祖先的历史提交，并且存储到临时文件中
				3.将当前部分指向主分支作为基底
				4.以当前基底开始，重新执行临时文件中的操作


				·切换到要要变基的分支
				·git rebase master
				·确定冲突文件修改方式
				·git switch master
				·git merge BRANCHNAME（fast forward）
				·git branch -d BRANCHNAME
			
			相对于merge而言，最终结果是相同的，但是变基会使得分支的合并图像消失，使得代码的提交记录更简洁
			在大型项目时，优先使用，具体以公司的实际情况而定
			注：大部分情况下变基和merge可以互换使用，但是如果分支已经提交给了远程仓库，这时尽量不要使用变基
			（多人协作情况慎用）
			

