创建Package Manager 库流程  
1、mkdir HYLearningSwiftNetwork  
2、cd HYLearningSwiftNetwork  
3、swift package init --type library  
至此HYLearningSwiftNetwork 创建完毕  

推送到github流程  
git init  
git add .  
git commit -m "first-commit"  
git remote add origin https://github.com/miaohy/HYLearningSwiftNetwork.git  
git push -u origin master  
git tag 0.1.1  
git push origin --tags  

由于事先已经在github上建立了master 分支，所以出现如下错误  
! [rejected] master -> master (non-fast forward)  
解决方法   
1、git pull origin master --allow-unrelated-histories //把远程仓库和本地同步，消除差异  
2、修改重复文件README.md  
3、git add README.md  
4、git commit -m "fix confilict"  
5、git push origin master  
上传成功到git  

工程中引入依赖包例子  
 .package(url: "https://github.com/miaohy/HYLearningSwiftNetwork.git", from: "0.1.1")  
 .target(  
            name: "HYLearningSPDemo",  
            dependencies: ["HYLearningSwiftNetwork"])  
            
  工程代码文件中引入  
  import HYLearningSwiftNetwork  
