# git 시작하기
# remote : github.com 계정에서 새로운 프로젝트를 만든다.
# local : 
#  - git 설치
git config --global user.name "ohh5986"
git config --global user.email "ohh5986@sk.com"
mkdir D:\works\eclipsews\boot  #create  working directory  :
cd D:\works\eclipsews\boot
git init
# create sample file & git push  sample file : readme.ohh.txt
git status
git add readme.ohh.txt
git commit -m "Add readme.ohh.txt"
git remote add origin https://github.com/ohh5986/boot.git
git push  # occur  error 
# fatal: The current branch master has no upstream branch.
# To push the current branch and set the remote as upstream, use
#
#    git push --set-upstream origin master  
git push --set-upstream origin master   #로그인 창에서 로그인 함 (ohh5986@sk.com / grape5hh!)
# ! [rejected]        master -> master (fetch first)
#error: failed to push some refs to 'https://github.com/ohh5986/boot.git'
#hint: Updates were rejected because the remote contains work that you do
#hint: not have locally. This is usually caused by another repository pushing
#hint: to the same ref. You may want to first integrate the remote changes
#hint: (e.g., 'git pull ...') before pushing again.
#hint: See the 'Note about fast-forwards' in 'git push --help' for details.

# 에러원인 github에서 레포지토리를 생성할 때, README.md 파일을 생성했기 때문이다.
# 해결
# git pull 명렁어로 github의 원격 레포지토리를 내 로컬로 불러와서(fetch) 합친다(merge.)
# 그리고 git push 명령어로 다시 원격 레포지토리에 업로드한다.
git pull origin master  # 에러 
# * branch            master     -> FETCH_HEAD
#fatal: refusing to merge unrelated histories
# 이미 존재하는 두 프로젝트의 기록(history)을 저장하는 드문 상황에 사용된다고 한다. 
# 즉, git에서는 서로 관련 기록이 없는 이질적인 두 프로젝트를 병합할 때 기본적으로 거부하는데, 이것을 허용해 주는 것이다.
git pull origin master --allow-unrelated-histories

git push origin master  # 정상적으로 remote에 push됨

Enumerating objects: 6, done.
Counting objects: 100% (6/6), done.
Delta compression using up to 12 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (5/5), 507 bytes | 507.00 KiB/s, done.
Total 5 (delta 0), reused 0 (delta 0)
To https://github.com/ohh5986/boot.git
   ef76c65..9b4037c  master -> master

# 다음은 eclipse와 git을 연결하는 방법

open perspective>git
3가지 방법이 있음
Add an existing local git repository
Clone a Git repository  --> remote clone, branch version맞춰서 
Create a new local Git repository


