# 997_How_to_git

I use atom and git bash.  

***

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

