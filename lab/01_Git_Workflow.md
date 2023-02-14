# initialize a Git repository locally
```shell
mkdir myWebApp
cd myWebApp
git init #Inizializza Git Repo Locale

#configura global settings mail and name per tracciare le commit
git config --global user.name "Marco Oliva"
git config --global user.email "oliva.marco00@gmail.com"
```
# Inizialize Application
```shell
dotnet new mvc #Create a new ASP.NET core application
code . #apri la workink dir in visual studio code
dotnet build #build application
dotnet run #start application
```
# Use Git 
prima di tutto aggiungi file .gitignore al repository e inserisci .vscode/* all'interno del file cosi da non fare il push dei file all'interno di quella cartella specificata, nel nostro repository remoto.
```shell
git status #mostra lo stato del repo
git add . #aggiunge in stage tutti i file 
git commit -m "first commit" #facciamo la prima commit in locale
```
# Use Branch 
```shell
git branch feature-devops-home-page #crea un nuovo branch dal main
git checkout feature-devops-home-page # ci spostiamo all'interno del nuovo branch
git branch --list #mostra tutti i branch creati
```
Now navigate to the file ~\Views\Home\Index.cshtml and replace the contents with the text below.
```C#
@{
    ViewData["Title"] = "Home Page";
}

<div class="text-center">
    <h1 class="display-4">Welcome</h1>
    <p>Learn about <a href="https://azure.microsoft.com/services/devops/">Azure DevOps</a>.</p>
</div>
```
Refresh the web app and see the changes
Now commit this changes:
```shell
git status

git add .

git commit -m "updated welcome page."

git status
```

# Marge in Main
```Shell
git checkout main #spostati nel main

git merge feature-devops-home-page #fai il marge del branch sul main (ossia aggiungi le modifiche e la storia del branch sul main)
git branch --delete feature-devops-home-page #elimina il branch 
```

# Inspect
```Shell
git log -v #mostra i la storia delle commit del branch in cui ti trovi
git log -p #mostra anche le modifiche effetuate con la commit
```
# Use Reset (quando fai un errore)
```Shell
git log -v #get the lastest id commit
git reset --hard <id-commit> #reset the main branch to the privious version before the commit
git log -v
```