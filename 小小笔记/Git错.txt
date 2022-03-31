出错信息：
To github.com:hotstarsplus/public-demo.git
 ! [rejected]        master -> master (non-fast-forward)
error: failed to push some refs to 'github.com:hotstarsplus/public-demo.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

解决方式：
这时就要使用 git pull origin master --allow-unrelated-histories //把远程仓库和本地同步，消除差异
然后在重新add 和 commit 相应文件
再使用git push -u origin master就能上传成功了。

思考：
一定要同步吗，不同步可不可以push？？
git push -f 强推的老哥 可太秀了....好使！！[捂脸]