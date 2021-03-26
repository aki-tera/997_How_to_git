# 997_How_to_git

I use atom/VS Code and git bash.  

## English!
https://qiita.com/Ted-HM/items/7dde25dcffae4cdc7923

## How to batch update pip packages
You run the following command by powershell.
```pip3 install --upgrade ((pip3 freeze) -replace '==.+','')```

***
## How to add all

|-|New Files|Modified Files|Deleted Files|Current Directory|Subordinate directory|
|:---:|:---:|:---:|:---:|:---:|:---:|
|git add -u|×|○|○|○|×|
|git add -A|○|○|○|○|×|
|git add .|○|○|○|○|○|  
  
***
## How to write comment
- feat: A new feature
   - 新しい機能
- fix: A bug fix
   - バグの修正
- docs: Documentation only changes
   - ドキュメントのみの変更
- style: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)
   - 空白、フォーマット、セミコロン追加など
- refactor: A code change that neither fixes a bug nor adds a feature
   - 仕様に影響がないコード改善(リファクタ)
- perf: A code change that improves performance
   - パフォーマンス向上関連
- test: Adding missing or correcting existing tests
   - テスト関連
- chore: Changes to the build process or auxiliary tools and libraries such as documentation generation
   - ビルド、補助ツール、ライブラリ関連

***
## fetch from remote  
## (pull = fetch + merge, fetch:master@remote -> origin/master@local, merge:origin/master@local -> master@local)
you must operate the follow in order.  
[local:master@bush]git fetch origin master  
[local:master@bush]git pull origin master

## push local to remote
[local:master@VSCode]you commite files.  
[local:master@bush]git push origin master  


## delete branch 
[local:master@bush]git branch --merged  
[local:master@bush]```git branch --delete develop```

## discard files(unsaged changes)
[local:master@bush]```git checkout .```  

## reflect master in develop 
[local:master@bush]git checkout master  
[local:master@bush]git pull origin master  
[local:develop@bush]git checkout develop  
[local:develop@bush]git rebase master  

## back to old Commits
[local:branch-name@bush]git reset --hard "Commits id which you want to be"  
[local:branch-name@bush]git push -f origin HEAD^:branch-name  

***

## merge develop's branch to master's branch  
[local:develop@atom]  push feche buttom if you need to merge remoto ato github.  
[local:develop@atom]  discard something in stage of develop.  
[local:develop@bush]  ```git checkout master```  
[local:master@atom]  discard something in stage of master  
[local:master@bush]  ```git merge --no-ff develop```  

[referrence URL in japanese](https://sinsoku.hatenadiary.org/entry/20111025/1319497900)  

***

## merge remoto(github) to local(git)  
[local:master@atom]  discard something in stage of master  

master@remoto -->>  master@local  
[local:master@bush]  ```git pull origin master```  

*If trouble occurs, follow the steps below.*  
[local:master@bush]  ```git merge --abort```  
[local:master@bush]  ```git reset --hard HEAD```  

*If trouble coours, you can also force to merge.*  
[local:master@bush]  ```git fetch origin master```  
[local:master@bush]  ```git reset --hard origin/master```  

***

## clone a repository on GitHub to local(git)  
You get URL of clone.  
[local:master@bush]  ```git clone git@github.com:aki-tera/997_How_to_git.git```

## How to display the tree by Git Bash
[local:master@bush]  ```git graph```
  
Add the following to "$HOME/.gitconfig" or "/etc/gitconfig"  
```
[alias]  
    graph = log --graph --date-order -C -M --pretty=format:\"<%h> %ad [%an] %Cgreen%d%Creset %s\" --all --date=short
```
