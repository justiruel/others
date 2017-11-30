# GIT / Distributed VIersion Control System (DVCs)

## Recomended IDE
- smartgit (linux)
- sourcetree (windows)

## Perintah dasar

### Membuat git baru
```
git init
```
### set config
```
git config user.name tafsirul
git config user.email tafsirul@gmail.com
```
### show remote url
```
git remote -v  
```
### Clone
```
git clone https://github.com/justiruel/sql_server_learn.git 
```
### Add all edited data
```
git add *
```
### commit all data which has been added
```
git commit -m "komentar" 
```
###  Push to server
```
git push origin tafsirul
```
###  Show file which not committed
```
git status
```

### show committed/merged/rebased/pull file
```
git log --graph --oneline --all
```
###  Switch to branch devel
```
git checkout devel
```
### switch to and create branch tafsirul
```
git checkout -b tafsirul
```
### Add origin
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

### Pull
```
git pull origin master --> update semua data di origin/server kedalam active local branch
beda pull dan fetch : http://ngoprek.rahmad.my.id/2012/02/belajar-git-dasar-dasar-pengelolaan.html
```

### stash
```
git stash save --keep-index --include-untracked   --> menyimpan uncommitted
git stash apply --> mengembalikan uncommitted 
```

## Melihat perubahan pada revisi tertentu

```
git diff cf08ca0837cf26f1c595be36bb3a6b815e311be1    -> ini adalah nomor revisi diambil dari "git log"
git diff index.html
```
ref : https://www.petanikode.com/git-diff/


### If you want to see what you haven't git added yet:
```
git diff myfile.txt
```
### or if you want to see already-added changes
```
git diff --cached myfile.txt
```
catatan : untuk keluar dari view file tekan "q"


## Mencari tahu siapa yang melakukan commit, dan pada jam berapa
```
git blame index.html
```

# pull request
????


## 

<br/>
<i>NB: data dalam git kalau dihapus lalu di-commit tidak akan bener-benar dihapus</i>
