# 347Conteneurs
# Documentation d'installation de l'environnement de developpement.
## **Objectifs et consignes:** Cmder, Git, VSC, Docker Desktop.
--------------------------------------------------------------------------
**Objectifs**
À l'aide des sources proposées ci-dessous, installer différents outils proposés:
* Cmdr,
* Git,
* Visual Studio Code,
* Docker Desktop.

**Livrable**
La documentation d'installation favorise:
* Une documentation basée sur des lignes de commandes en mentionnant les INUTS et les OUTPUT attendus.
* Des captures d'écran lorsque les lignes de commmandes ne sont pas possible
* Une documentation de résolution d'éventuelles panne.

**Source du document initial:** `[Source](https://ivanskodje.com/how-to-set-system-path-environment-variable-in-windows-10/)`
                                             
**Cmder – Utilitaire de ligne de commande.**
### Context  
Cmder est un logiciel créé à cause de la pure frustration face à l’absence de jolis  émulateurs de consoles sur Windows. 
C’est donc un  émulateur de terminal pour Windows.
### Ce qu'on va faire
* **`[Télécharger](https://cmder.app/)`**
* Choisir la version mini (nous installerons *git* dans un second temps)
* Bien mettre à jour la variable d'environnement "*PATH*"
* En t'aidant de **`[cette documentation](https://github.com/cmderdev/cmder#shortcut-to-open-cmder-in-a-chosen-folder)`**, 
* fais en sorte que "*cmder*" s'ajoute au menu contextuel de l'explorateur de Windows. 

### **Test d'acceptations**
* Valider que la variable "PATH" a bien été mise à jour:
Utiliser la commande *`cmder`* pour ouvrir le prompt cmder.
(Dans l'exemple du prof il fallait mettre run cmder mais run n'est pas reconnu)
* Il faut valider que les raccourcis cmder ont bien été intégré dans l'explorateur de windows:
Pour ça il faut faire un clique-droit sur un dossier quelconque et *Cmder Here* sera dans les options.

## **1.Installation de *Cmder* ** et paramétrage de variable d'environnement
### Context
L'objectif est de pouvoir ouvrir/lancer *Cmder.exe* via laligne de commande, peut importe le chemin du répertoire.
En effet, sans l'ajout de la *variable d'environnement du chemin système*, 
il n'est pas possible d'exécuter Cmder.exe en dehors du fichier dans lequel il se trouve.
Dans cet exemple on va découvrir comment installer et exécuter **cmder** à partir de la ligne de commande.
On peut le faire avec n'importe quel fichier exécutable.

### Marche à suivre
1. Télécharger le *Cmder.exe* en version mini et le décompresser. 
Voici une image d'à quoi ressemble le dossier décompressé.
![](images/contenuDossierCmderMini.png "Contenu Décompressé")
2. Ouvrir l'invite de commande en tant qu'administrateur 
(en faisant un clique-droit sur le terminal dans l'explorateur windows).
Avec  le terminal, se positionner dans le dossier cmder avec le chemin d'accès via la commande
`cd C:\cmder_mini` Là où j'ai mis "C:\cmder_mini", il faut le remplacer par le chemin d'accès du dossier sur ton ordi.
Tu peux le trouver en allant sur le dossier cmder, en cliquant sur la partie sélectionnée sur l'image et en copiant le chemin d'accès qui se trouve en haut.
![](images/cheminDacces.png "Chemin d'accès")
~~3. Ensuite il faut sauvegarder le chemin d'accès en écrivant cette ligne de code `.\cmder.exe /REGISTER ALL`~~  
~~Et enfin lancer la commande `cmder.exe` pour ouvrir l'app.~~
### PROBLÈME! 
ça ne marche pas car la variable d'environnement PATH n'a pas encore été configurée
pour indiquer à windows où se trouve le dossier `"C:\cmder_mini"`. On passe donc à la partie 2.

## **2.Paramétrage de variable d'environnement **
### Contexte
Les **"Variables d'environnement système"**, 
appelée la variable d'environnement du chemin système,
est utilisée dans le contexte de l'exécution des fichiers.exe via la ligne de commande 
ou la fenêtre PowerShell.

### Marche à suivre
* Même étapes qu'avant: télécharger en mini, décompresser, se souvenir du chemin d'accès.
On l'a déjà fait donc je le compte pas.
1. Dans le champ **Rechercher** du menu Démarrer, taper *envi* 
et ouvrir la page **Modifier les variables d'environnement système**, puis sélectionner Variable d'environnement
Dans la nouvelle fenêtre, aller dans le menu Variables système.
Sélectionner la ligne commençant par **PATH** et cliquer sur **Modifier**.
2. Dans la nouvelle fenêtre, cliquer sur **Nouveau** 
puis **Parcourir** pour sélectionner le dossier **cmder** qui contient le fichier exécutable de l’application. 
Une nouvelle ligne  avec le chemin complet de l’application cmder s’ajoute à la liste 
![](images/envi.png "Environnement")
3. Cliquer 3 fois ok pour fermer les fenêtres de configuration ouvertes.
4. Ouvrir **l'invite de commande** ou **PowerShell**. Si c'est déjà ouvert, faut le refermer et le rouvrir (toujours en admin).
taper `cmder.exe` et appuyer sur Entrée.
5. L'exécution de la commande ci-dessus ouvre le terminal **Cmder**.
![](images/UnblockContinue.png "Unblock and Continue")
Faire des mises à jour si besoin.

## **3.Raccourci pour ouvrir Cmder dan un dossier choisi ** 
### Marche à suivre
1. ouvrir un terminal en tant qu'administrateur.
2. Accéer au répertoire dans lequel on a placé _Cmder_ 
En remettant le bon chemin d'accès "C:\cmder_mini" via la commande
`cd C:\cmder_mini` dans le terminal en mode admin.
3. Exécuter `.\cmder.exe /REGISTER ALL`
C'est ette commande qui va permettre l'option d'ouvrir Cmder automatiquement 
lors d'un clique-droit dans un dossier ou sur le bureau de l'explorateur Windows.
4. Dans une fenêtre d'explorateur de fichiers, faites un clic-droit dans ou sur
un répertoire pour voir "Cmder Here" dans le menu.

### **Test d'acceptation**
1. Valider que l variable "PATH" a bien ltl mise à jour en tapant cette commande `cmder`
Normalement ça va ouvrir le prompt cmder.
2. Valider que les raccourcis cmder ont bien été intégré dans l'explorateur de Windows
![](images/raccourciClic.png "Raccourci Cmder")
        
## **Gestion de versioning**
**1. Git - outil de gestion de version**
### Context
Git est un système de contrôle de version distribué gratuit et open source conçu 
pour gérer tout, des petits aux très grands projets, avec rapidité et eff
icacité.
* **[Télécharger](https://git-scm.com/)** 
* Prendre la version *"Standalone Installer"* 
* Laisser tous les paramètres par défaut (durant l’installation) 