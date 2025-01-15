# Git (cli) - 1.část
Zjisti jestli máš Git nainstalovaný na tvém počítači
```
git --version
git version 2.34.1
```

Pokud je Git nainstalován, měl by zobrazovat něco jako git verze X.Y

## Konfigurace Gitu
Nyní dej Gitu vědět, kdo jsi. To je důležité pro systémy správy verzí, protože pro každý commit Git používá tyto informace:

```
git config --global user.name "jmeno"
git config --global user.email "e-mail"
```

Změň uživatelské jméno a e-mailovou adresu na vlastní. Pravděpodobně to budeš chtít použít také při pozdější registraci na GitHub.

## Vytvoření projektu - Git Repository (Repo)

Nyní vytvoř novou složku pro svůj projekt a nastav ji jako pracovní adresář:

```
mkdir myproject
cd myproject
```
Nyní provedeme inicializaci Gitu:

```
git init 
Initialized empty Git repository in /Users/user/myproject/.git/
```
Nyní máš vytvořené Git Repository.

## Přidání nového souboru do Git Repository

Tvoje nové repo nyní existuje, ale je prázdné. Nyní do něj přidej soubor index.html s následujícím obsahem. (Vytvoř jej pomocí libovolného textového editoru)

```
<!DOCTYPE html>
<html>
<head>
<title>Hello World!</title>
</head>
<body>

<h1>Hello world!</h1>
<p>This is the first file in my new Git Repo.</p>

</body>
</html> 
``` 
Nyní přejdi do terminálu a ověř si, zda soubor index.html v Git Repository existuje.
```
ls
index.html
```
Příkaz ls vypíše soubory ve tvém Repu. Jestli je vše v pořádku vypíše se ti index.html, zatím jediný soubor ve tvém Repu.</br> Nyní ověř status Repa a zjisti, jestli je nový soubor jeho součástí.
```
git status
On branch master

No commits yet

Untracked files:
  (use "git add ..." to include in what will be committed)
    index.html

nothing added to commit but untracked files present (use "git add" to track)
```
