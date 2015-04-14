####创建开发分支
* 根据master分支创建develop分支。develop分支将包含所有历史记录。

####开发新功能
* 开发新模块基于develop分支生成feature

	编辑、暂存、提交

* 开发完成后将代码合并到develop分支，并push到远程仓库

####发版
* 准备发版，基于develop创建release分支。该版本是功能冻结的，任何不在develop分支中的新功能都推到下个发布循环中。

* 发版成功后，合并到master和develop分支中，并删除release分支。master分支创建tag便于追踪。

####bug修复
* 上线后由用户提报的bug，直接基于master分支创建issue(hotfix)分支。解决后合并到master和develop分支，并移除issue分支	