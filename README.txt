
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
		查看分支
			git branch
		创建新分支
			git branch BRANCHNAME
		