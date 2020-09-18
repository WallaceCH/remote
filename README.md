# 원격 저장소 활용하기

## 충돌 상황

* 원격 저장소의 이력과 로컬 저장소의 이력이 다르다.

```bash
$ git push origin master
To https://github.com/WallaceCH/remote.git
 ! [rejected]        master -> master (fetch first)
# 에러
error: failed to push some refs to 'https://github.com/WallaceCH/remote.git'
# rejected(거절) - 원격저장소의 작업이 로컬에 없다!!!
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
# 너는 원할 것 같다.. 원격저장소의 변경사항을 먼저 통합(integrate) 다시 push하기 전에
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

```

* 해결 방법

  ```bash
  $ git pull origin master
  ```

  * 이렇게 하면, vim 창으로 

  ```bash
  s
  ```

  

  * 자동으로 작성된 커밋메세지를 확인하고, `:wq` 로 저장하고 나간다.

  * 그 이후 log를 확인하고, push 한다.

    ```bash
    $ git log --oneline
    e15655a (HEAD -> master) Merge branch 'master' of https://github.com/WallaceCH/remote into master
    625aec9 update local
    9c9102a (origin/master) Create remote.txt
    4c0d48c WallceCH first
    ```

    

  



