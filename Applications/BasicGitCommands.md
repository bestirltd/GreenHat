# Basic Git Notes


##### New Repo
```
echo "# temp" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/<username>/<repo_name>.git
git push -u origin master
```

##### upload an existing repository to newly created repo
```
git remote add origin https://github.com/<username>/<repo_name>.git
git push -u origin master
```

##### Add changes to repo
```
git add --all
#Or can add single file/s
git add README.md

git commit -m "message"
git push
```


##### Pull changes from remote
`git pull`



## Gitea_Self_Hosted_Notes
IF using https (self signed) for the pull and push and maybe even fetch you need to add http.sslVerify=false 

```
git init
git add --all
git commit -m "first commit"
git remote add origin https://localhost:3000/<username>/<repo>.git
git -c http.sslVerify=false push -u origin master
```

To push changes to a repo 
```
git add *
git commit -m "update notes"
git push 
#If selfsigned ssl
git -c http.sslVerify=false push
```    
 If master branch is proctected you will need to create a branch, make pull request and merge to master repo.
 This is a good way to stop you mucking up your main repo.

``` 
git checkout -b [name_of_your_new_branch]   # i called mine newgreen
git checkout newgreen						# change working copy to [name_of_your_new_branch] this happen auto when created new branch
git -c http.sslVerify=false push origin newgreen
```
 
If you made changes just to local then just add, commit, push
```
git add --all
git commit -m "some stuff"
git -c http.sslVerify=false push
```

If you made changes to remote then you need to pull to update local.
```
git -c http.sslVerify=false pull    # if its a self signed ssl -c needed
```
    
If you made changes to local and remote, then first pull, add, commit, push (this may be wrong need to look into syncing)

Download a repo
```
git clone -c http.sslVerify=false https://192.168.1.113:3000/<username>/<repo_name>.git
```
	
	

    
