# Git (cli) - 2.část

## Git staging area
Jednou ze základních funkcí Gitu jsou koncepty prostředí Staging area a Commit.
Při práci můžeš přidávat, upravovat a odebírat soubory. Ale kdykoli dosáhneš nějakého milníku nebo dokončíš část práce, přidej soubory do prostředí Staging area. Připravené soubory ve Staging area jsou připraveny k odeslání do úložiště pomocí commitu. Brzy se o commitu dozvíš víc.</br>
![](git-areas.png)</br>
Pro tuto chvíli jsme dokončili práci s index.html. Můžeš jej tedy přidat do prostředí Staging area:

```
git add index.html
```
Soubor index.html by měl být přidán do staging area. Ověř si to pomocí příkazu git status:</br>

```
git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached ..." to unstage)
    new file: index.html
```

Jestli vidíš stejný výpis, byl soubor index.html přidán do staging area.

## Přidání více souborů do staging area

Nyní vytvoř soubor readme.md s následujícím obsahem:

```
# Vítej v Gitu

Toto je cvičný repozitář pro Git tutorial.</br>
Tutorial byl vytvořen podle https://www.w3schools.com/git.
```

Dále vytvoř soubor bluestyle.css s obsahem:

```
body {
background-color: lightblue;
}

h1 {
color: navy;
margin-left: 20px;
} 
```

Pozn: Vysvětli jaké informace soubor bluestyle.css obsahuje a jak se tyto informace projeví v HTML stránce.

Uprav soubor index.html přidáním odkazu na soubor bluestyle.css.

```
<!DOCTYPE html>
<html>
<head>
<title>Hello World!</title>
<link rel="stylesheet" href="bluestyle.css">
</head>
<body>

<h1>Hello world!</h1>
<p>This is the first file in my new Git Repo.</p>

</body>
</html> 
```

Nyní přidej všechny tři soubory do staging area příkazem:

```
git add --all
```

Použití --all místo jednotlivých názvů souborů způsobí zachycení všech změn souborů (nových, upravených i smazaných).

Ověřte stav pomocí příkazu git status:

```
git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached ..." to unstage)
        new file:   README.md
        new file:   bluestyle.css
        new file:   index.html
```
Nyní byly všechny tři soubory přidány do staging area.

Pozn: **git add --all** můžeme zkrátit pomocí **git add -A**

## Git commit
Když dokončíš práci je třeba potvrdit tento krok pomocí commitu.

Commity sledují tvůj pokrok a změny během práce. Git registruje každý bod změny jako bod uložení. Je to bod v projektu, ke kterému se můžeš vrátit, pokud najdeš chybu nebo chceš provést změnu zpět.

Každý bod uložení by měl mít svoji **zprávu** o tom, co se v repozitáři změnilo. Podle těchto zpráv se pak můžeš ty i ostatní snadno orientovat.

```
git commit -m "First release of Hello World!"
[master (root-commit) 221ec6e] First release of Hello World!
 3 files changed, 26 insertions(+)
 create mode 100644 README.md
 create mode 100644 bluestyle.css
 create mode 100644 index.html
 ```
 
 Příkaz commit provede potvrzení a parametr -m přidá zprávu.

Staging area se přenesla do repa se zprávou:
"First release of Hello World!"

## Git commit bez předchozího přesunutí do staging area

Někdy, zvláště když uděláš pouze malé změny, je výhodné sloučit přesunutí do staging area a následný commit do jednoho příkazu commit s parametrem -a.

Proveď například malou změnu v souboru index.html


```
<!DOCTYPE html>
<html>
<head>
<title>Hello World!</title>
<link rel="stylesheet" href="bluestyle.css">
</head>
<body>

<h1>Hello world!</h1>
<p>This is the first file in my new Git Repo.</p>
<p>A new line in our file!</p>

</body>
</html> 
```

Nyní ověř stav pomocí git status, ale tentokrát použij parametr --short a dostaneš mnohem kompaktnější výpis.

```
git status --short
 M index.html
```

Velké M před názvem souboru znamená modified. Zkrácené výpisy vypadají takto:

- ?? - Untracked files
- A - Files added to stage
- M - Modified files
- D - Deleted files

Nyní proveď commit s parametrem -a, bez předchozího git add:

```
git commit -a -m "Updated index.html with a new line"
[master 09f4acd] Updated index.html with a new line
 1 file changed, 1 insertion(+)
```

**Commit bez předchozího přesunutí do staging area není všeobecně doporučován, protože někdy může vést k nechtěným změnám.**

## Historie commitů

pro zobrazení historie commitů tvého repozitáře použij příkaz:

```
git log
commit 09f4acd3f8836b7f6fc44ad9e012f82faf861803 (HEAD -> master)
Author: w3schools-test 
Date:   Fri Mar 26 09:35:54 2021 +0100

    Updated index.html with a new line

commit 221ec6e10aeedbfd02b85264087cd9adc18e4b26
Author: w3schools-test 
Date:   Fri Mar 26 09:13:07 2021 +0100

    First release of Hello World!
```


## Když si v Gitu nevíš rady

Když si v Gitu nebudeš vědět rady můžeš použít některý z následujících příkazů:
```
git  command -help
```

tento help vypíše nápovědu k specifikovanému příkazu.

```
git help --all
```

tento help vypíše všechny dostupné příkazy gitu.