# reset vs revert

## reset

> 커밋 히스토리 사라지니 주의 할 것

* `--hard` : reset 하기전 SA, WD 모든 작업 리셋
* `--mixed` : (기본) SA reset. WD 작업은 남겨둠
* `--soft` : reset 하기전까지 했던 SA, WD 작업은 남겨둠

```bash
$ git log --oneline
ce77c2d (HEAD -> master) omit & real
c01f908 Add no.txt
d547a8a !!!
d6109cf Add a.txt
585183f Add README

$ git reset --hard d547a8a
HEAD is now at d547a8a !!!

$ git log --oneline
d547a8a (HEAD -> master) !!!
d6109cf Add a.txt
585183f Add README

```

## revert

```bash
$ git log --oneline
d547a8a (HEAD -> master) !!!
d6109cf Add a.txt
585183f Add README

$ git revert d547a8a
Removing sori.txt
hint: Waiting for your editor to close the file..[master 6487ffd] Revert "!!!"
 3 files changed, 11 deletions(-)
 delete mode 100644 sori.txt

$ git log --oneline
6487ffd (HEAD -> master) Revert "!!!"
d547a8a !!!
d6109cf Add a.txt
585183f Add README

```

