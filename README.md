MANUAL BÁSICO DO GIT --> https://githowto.com/pt-BR

----------------------------------------------------------------------------------------------------------------
###	LISTANDO ALTERAÇÕES NAS BRANCHES ###
 
 "git log shows the commit log accessible from the refs (heads, tags, remotes)"
 "git reflog is a record of all commits that are or were referenced in your repo at any time."
 
- Visualizar os últimos 10 commits realizados
>git log  HEAD~10..HEAD --pretty=oneline -10
 
- Mostrar os últimos 10 acontecimentos na branch
>git reflog -10
----------------------------------------------------------------------------------------------------------------

### LISTANDO BRANCHES ###

- To see local branches, run this command:
>git branch
- To see remote branches, run this command:
>git branch -r
- To see all local and remote branches, run this command:
>git branch -a
------------------------------------------------------------------------------------------------------------------

### MANUSEANDO NOMES DE BRANCHES ###
 
- Rename your local branch.
If you are on the branch you want to rename:
>git branch -m new-name

- If you are on a different branch:
>git branch -m old-name new-name

- Delete the old-name remote branch and push the new-name local branch.
>git push origin :old-name new-name

- Reset the upstream branch for the new-name local branch.
Switch to the branch and then:
>git push origin -u new-name

------------------------------------------------------------------------------------------------------------------

### RESET ###

- excluir todos os stages e commits locais e equalizar com a master remota
>git reset --hard origin/master

------------------------------------------------------------------------------------------------------------------

### CRIANDO ALIAS ###

- Alias
git config --global alias.coa "!git add -A && git commit -m"
git coa "A bunch of horrible changes"

- Método
gcaa() { git add --all && git commit -m "$*" }
gcaa This is the commit message

------------------------------------------------------------------------------------------------------------------

- procurar branches por padrão de nome
>git branch | grep "<pattern>"  (linux)
>git branch | findstr "<pattern>"  (windows)

- excluir  branches por padrão
>git branch | grep "<pattern>" | xargs git branch -D (linux)
-------------------------------------------------------------------------------------------------------------------