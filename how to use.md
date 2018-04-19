1, 从现有的项目上传：

Step 1: Switch to your repository's directory

  `cd /path/to/your/repo`
  
Step 2: Connect your existing repository to Bitbucket

  `git remote add origin git@bitbucket.org:ZhangDuo1/abc.git`
  
  `git push -u origin master`
  
2，从头开始：

```git clone git@bitbucket.org:ZhangDuo1/abc.git

 cd abc

 echo "# My project's README" >> README.md

 git add README.md

 git commit -m "Initial commit"

 git push -u origin master```
