# homework
作业提交仓库
## 仓库目录说明

根目录下包含一些git配置文件，以及一些子目录，每一个子目录都是一个独立的作业或者问题，该独立问题的目录下会又一个Markdown文件描述该问题，以及答题格式，以及其他目录代表每个人的作业答案， 作业答案目录是每个作业人的名字

```
root
│   README.md
│   somecomfigfiles  
│
└───Problem1
│   │   commit_name.txt
│   │   problemdescription.txt
│   │
│   └───Username
│       │   answerFile1.txt
│       │   answerFile2.txt
│       │   ...
│   
└───Problem2
    │   commit_name.txt
    │   problemdescription.txt
```

## 代码提交说明
master 分支是受保护分支，除去管理员外其他人都不能直接push代码到该分支， 作业提交人员提交做的形式是先new出自己的作业分支（命名形式--作业内容_提交人名字）在该新建分支下提交自己的作业内容，然后完成后再向master分支提交push request或者merge code 请求