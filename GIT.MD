## Recomended IDE
- smartgit (linux)
- sourcetree (windows)

## Perintah dasar

```
git remote -v  --> show remote url
```
```
git clone https://github.com/justiruel/sql_server_learn.git 
```
```
git add * --> add all edited data
```
```
git commit -m "komentar" --> commit all data which has been added
```
```
git push origin tafsirul --> push to server
```
```
git status --> show file which not committed
```
```
git log --graph --oneline --all --> show committed file
```
```
git checkout devel --> switch to branch devel
```
```
git checkout -b tafsirul --> switch to and create branch tafsirul
```
```
git config user.name tafsirul
git config user.email tafsirul@gmail.com
```

```
git remote add origin https://github.com/justiruel/sql_server_learn.git
git remote remove origin
```

### Merge
```
git checkout master
git merge devel
```

### Rebase
Rebase memiliki fungsi yang sama dengan merge, bedanya operasi merge akan menghasilkan commit baru sementara rebase tidak, hasil log dari rebase akan terlihat lebih rapi (tidak ada percabangan)

```
git checkout master
git rebase devel
jika ada conflict perbaiki
git add *
git rebase --continue
```

```
git pull origin master --> update semua data di origin/server kedalam active local branch
beda pull dan fetch : http://ngoprek.rahmad.my.id/2012/02/belajar-git-dasar-dasar-pengelolaan.html
```

## stash

```
git stash save --keep-index --include-untracked   --> menyimpan uncommitted
git stash apply --> mengembalikan uncommitted 
```
