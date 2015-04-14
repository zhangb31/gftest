####创建开发分支

![image](https://github.com/zhangb31/gftest/blob/master/img/git-flow-createdev.png?raw=true)

* 根据master分支创建develop分支。develop分支将包含所有历史记录。

	  $>git checkout -b develop

	  $>git push origin develop

* 其他开发者在develop分支开发。

		$>git clone ssh://user@host/path/to/repo.git
		
		$>git checkout -b develop origin/develop

####开发新功能

![image](https://github.com/zhangb31/gftest/blob/master/img/git-flow-newfeature.png?raw=true)

*	暂存当前开发环境，pull最新develop

		$>git stash save '提示信息'

		$>git pull origin develop


* 开发新模块基于develop分支生成feature

	编辑、暂存、提交
	
		git status
		
		git add
		
		git commit
		
![image](https://github.com/zhangb31/gftest/blob/master/img/git-flow-featurefinishes.png?raw=true)

* 开发完成后将代码合并到develop分支，并push到远程仓库

		$>git pull origin develop
		
		$>git checkout develop
		
		$>git merger feature-*
		
		$>git push origin develop
		
		$>git branch -d feature-*
		
		#移除远端分支
		$>git push origin :branch-name


####发版

* 准备发版，基于develop创建release分支。该版本是功能冻结的，任何不在develop分支中的新功能都推到下个发布循环中。

* 发版成功后，合并到master和develop分支中，并删除release分支。master分支创建tag便于追踪。

####bug修复
* 上线后由用户提报的bug，直接基于master分支创建issue(hotfix)分支。解决后合并到master和develop分支，并移除issue分支