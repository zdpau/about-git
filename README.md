# about-git
https://git-scm.com/book/zh/v2

一，起步

1.1版本控制：版本控制是一种记录一个或若干文件内容变化，以便将来查阅特定版本修订情况的系统。

  1，本地版本控制系统，其中最流行的一种叫做 RCS，mac仍能使用RCS命令。
     https://git-scm.com/book/en/v2/images/local.png
     它的工作原理是在硬盘上保存补丁集（补丁是指文件修订前后的变化）；通过应用所有的补丁，可以重新计算出各个版本的文件内容。
     
  2，集中化的版本控制系统（Centralized Version Control Systems，简称 CVCS）
     https://git-scm.com/book/en/v2/images/centralized.png
     这类系统，诸如 CVS、Subversion 以及 Perforce 等，都有一个单一的集中管理的服务器，保存所有文件的修订版本，而协同工作的人们都通过客户端连到这台服务器，取出最新的文件或者提交更新。缺点是中央服务器的单点故障。 如果宕机一小时，那么在这一小时内，谁都无法提交更新，也就无法协同工作。
     
  3.分布式版本控制系统（Distributed Version Control System，简称 DVCS）
    https://git-scm.com/book/en/v2/images/distributed.png
    在这类系统中，像 Git、Mercurial、Bazaar 以及 Darcs 等，客户端并不只提取最新版本的文件快照，而是把代码仓库完整地镜像下来。 这么一来，任何一处协同工作用的服务器发生故障，事后都可以用任何一个镜像出来的本地仓库恢复。 因为每一次的克隆操作，实际上都是一次对代码仓库的完整备份。
    
1.2 Git 和其它版本控制系统（包括 Subversion 和近似工具）的主要差别在于 Git 对待数据的方法。 概念上来区分，其它大部分系统以文件变更列表的方式存储信息。 这类系统（CVS、Subversion、Perforce、Bazaar 等等）将它们保存的信息看作是一组基本文件和每个文件随时间逐步累积的差异。
  https://git-scm.com/book/en/v2/images/deltas.png 
  
  Git 不按照以上方式对待或保存数据。 反之，Git 更像是把数据看作是对小型文件系统的一组快照。 每次你提交更新，或在 Git 中保存项目状态时，它主要对当时的全部文件制作一个快照并保存这个快照的索引。 为了高效，如果文件没有修改，Git 不再重新存储该文件，而是只保留一个链接指向之前存储的文件。 Git 对待数据更像是一个快照流。https://git-scm.com/book/en/v2/images/snapshots.png

Git 保证完整性： Git 中所有数据在存储前都计算校验和，然后以校验和来引用。 这意味着不可能在 Git 不知情时更改任何文件内容或目录内容。 这个功能建构在 Git 底层
