# GIT CONVENTION
## Macam Branch
- Branch Fitur => setiap feature mempunyai branch tersendiri
- Branch Bugs =>  setiap bugs yang signifikan akan dibuatkan branch tersendiri
- Other Branch => develop, uat, master

## Contoh kasus
- Branch Feature
```
F-1
F-2
F-3
F-4
```
- Other Branch
```
develop
uat
master
```
- Branch Bugs
```
B-1-1
```
## Pseudo Code
```
membuat_branch_feature_dari_branch_develop()
if (branch feature selesai dikerjakan dan tested by developer){ 
	merge_branch_feature_ke_branch_develop()
	deploy_branch_develop_ke_server_stagging()
}


if (saat sprint review ditemukan bugs){
	if (bugs signifikan){
		membuat_branch_bugs_dari_branch_develop()
		perbaiki()
		merge_branch_bugs_ke_branch_develop()
		deploy_branch_develop_ke_server_stagging()
	}else{
		kerjakan_bug_fix_di_branch_feature()
		kembali_merge_branch_feature_ke_branch_develop()
		deploy_branch_develop_ke_server_stagging()
	}
}

if(saatnya UAT){
	merge_branch_develop_ke_branch_uat()
	deploy_branch_uat_ke_server_uat()
}

if (saat uat ditemukan bugs){
	membuat_branch_bugs_dari_branch_develop()
	perbaiki()
	merge_branch_bugs_ke_branch_develop()
	merge_branch_develop_ke_branch_uat()	
	deploy_branch_uat_ke_server_uat()
}

if (saatnya production){
	merge_branch_uat_ke_branch_master()
	deploy_branch_master_ke_server_production()
}
```  
