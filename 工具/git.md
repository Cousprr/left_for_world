## git ����ָ��

### ����

`git init` ��ʼ��

`git add target_file` �� `git add .` ����ļ����ݴ���

`git commit -m "first commit"` �ύ�ݴ����ļ����ֿ���

`git remote add origin https://github.com/username/reponame.git` ����Զ�ֿ̲�

`git push -u origin master` ���ʹ��뵽Զ�ֿ̲�

`git pull upstream master` ��ȡԶ�ֿ̲����´���

### git config
`git config --list` �鿴������Ϣ  
`git config --global user.name "xxx"`  
`git config --global user.email "xxx@xxx.com"`

### git clone

`git clone https://github.com/username/reponame.git`

### git branch

`git branch` �鿴���ط�֧

`git branch -r` �鿴Զ�̷�֧

`git branch -a` �鿴���з�֧

`git branch new_branch` �����·�֧

`git checkout new_branch` �л����·�֧

`git checkout -b new_branch` �������л����·�֧

`git push --set-upstream origin <branch-name>` ���͵�����������������ڣ�Զ�̷�֧

`git branch -d new_branch` ɾ�����ط�֧

`git push origin --delete new_branch` ɾ��Զ�̷�֧

## ������

1
```
ssh: connect to host github.com port 22: Connection refused
```
��˼��ssh���Ӳ���github 22�˿ڣ�һ���Ǽ��������⣬�����watt�ص��ͺ���

2
```
warning: LF will be replaced by CRLF the next time Git touches it
```
��˼��git���ύʱ�����LF�滻��CRLF����ΪgitĬ��ʹ��LF��Ϊ���з�����windowsʹ��CRLF��Ϊ���з�

������뿴warning���Թص���ʹ��``git config --global core.autocrlf false``

3
```
error: src refspec main does not match any
error: failed to push some refs to 'github.com:Cousprr/left_for_world.git'
```
��˼�Ǳ��ط�֧mainû�к�Զ�̷�֧ƥ�䣬����ΪԶ�̷�֧��master������main�����Գ���``git push origin master``